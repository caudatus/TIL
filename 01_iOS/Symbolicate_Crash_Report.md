# Symbolicate Crash Report
앱 심사시 리젝과 함께 .txt파일로 crash report를 받았을때

1. .txt -> .crash 파일명 변경
2. 원하는 위치에 새로 폴더 생성 후 리포트 파일 복사
3. .dsym 파일 복사
4. .app 파일 복사
5. symbolicatecrash 파일 복사
6. 터미널에서 해당 폴더 위치로 이동 후 명령어 입력
   $ export DEVELOPER_DIR="/Applications/Xcode.app/Contents/Developer"
7. 변환 파일 생성
   $ ./symbolicatecrash 기존파일명.crash > 변환하여생성되는파일명.crash

<br/>

When you got your crash report in .txt file just follow these steps :

Change the file extension .txt to to .crash (eg mycrash.txt to mycrash.crash)
Create a new folder in desktop and copy mycrash.crash file to the newly created folder
Copy the .dsym file
xcode -> window -> orgnizer or xcode -> product -> Archive to open the Archives window :
Select any Archives of your app Right click on it Then select show in finder
You see aapname.xcarchive file Right click on it and select show package contents
You see dSYMs folder open it and get .dSYM file and paste it in the newly created folder
Copy the .app file from the same xcarchive
Go to Folder utility from Finder. (Shift + Cmd + G) Use the path /Applications/Xcode.app/Contents/SharedFrameworks/DVTFoundation.framework/Versions/A/Resources/

Find symbolicatecrash file and copy this file to the newly created folder

You should now have :
mycrash.crash
myapp.app
myapp.app.dSYM
symbolicatecrash
Open terminal cd your folder path and then type this
$ export DEVELOPER_DIR="/Applications/Xcode.app/Contents/Developer"
Type this symbolicate command on your crash
$ ./symbolicatecrash mycrash.crash > symbolicated.crash
[stackoverflow][1]

<br/>

## 한줄 바이너리 해석
해당 폴더 이동 후
xcrun atos -o 앱이름.app/앱이름 -arch arm64 -l (Load Address) (Address to symbolicate)

[Apple Documents][2]


[1]: https://stackoverflow.com/questions/40479835/how-to-symbolicate-crash-report-from-apple-received-in-txt-format-not-crash-fo
[2]: https://developer.apple.com/library/archive/technotes/tn2151/_index.html#//apple_ref/doc/uid/DTS40008184-CH1-SYMBOLICATE_WITH_ATOS
