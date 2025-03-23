커멘드 라인 인터페이스 프로그램
-----------------------------
<br>

<pre>
<code>
#define _CRT_SECURE_NO_WARNINGS
#include<stdio.h>
#include<tchar.h>
#include<locale.h>
#include<windows.h>


#define STR_LEN 256
#define CMD_TOKEN_NUM 10

TCHAR cmdString[STR_LEN];
TCHAR cmdTokenList[CMD_TOKEN_NUM][STR_LEN];
TCHAR seps[] = _T(" ,\t\n");

TCHAR promptMessage[STR_LEN] = _T("USW command >>");
int CmdProcessing(int);
int CmdTokenize(void);

int _tmain(int argc, TCHAR* argv[])
{
	_tsetlocale(LC_ALL, _T("korean"));

	DWORD isExit = NULL;
	int tokenNum = 0;
	if (argc >= 2) {
		for (int i = 1; i < argc; i++) {
			_tcscpy(cmdTokenList[i - 1], argv[i]);
		}
		tokenNum = argc - 1;
		isExit = CmdProcessing(tokenNum);
		if (isExit == TRUE)
		{
			_fputts(_T("명령어 처리를 종료합니다. \n"), stdout);
			return 0;
		}
	}
	while (1) {
		int tokenNum = CmdTokenize();

		if (tokenNum == 0) // Enter 입력시 처리
			continue;

		isExit = CmdProcessing(tokenNum);
		if (isExit == TRUE) {
			_fputts(_T("명령어 처리를 종료합니다. \n"), stdout);
			break;
		}
	}
	return 0;
}

int CmdTokenize()
{
	TCHAR* token;

	_fputts(promptMessage, stdout);
	_fgetts(cmdString, 256 , stdin);

	token = _tcstok(cmdString, seps);

	int tokenNum = 0;
	
	while (token != NULL) {
		_tcscpy(cmdTokenList[tokenNum++], _tcslwr(token));
		token = _tcstok(NULL, seps);
	}
	return tokenNum;
}



int CmdProcessing(int tokenNum)
{
	TCHAR ERROR_CMD[] = _T("'%s' 은(는) 실행할 수 있는 프로그램이 아닙니다.\n");
	TCHAR cmdStringWithOptions[STR_LEN] = { 0, };
	TCHAR optString[STR_LEN] = { 0, };

	if (!_tcscmp(cmdTokenList[0], _T("exit"))) {     //cmd 창에서 exit 을 입력하면 프로그램 종료
		return TRUE;
	}
	else if (!_tcscmp(cmdTokenList[0], _T("echo"))) {          //cmd 창에서 echo (text)입력하면
		for (int i = 1; i < tokenNum; i++)                     //echo (text) 출력
			_stprintf(optString, _T("%s %s"), optString, cmdTokenList[i]);
		_tprintf(_T("echo message : %s \n"), optString);  
	}
	else {
		_tprintf(ERROR_CMD, cmdTokenList[0]);
	}
	return 0;
	
}
</code>
<pre>