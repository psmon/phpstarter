# phpstarter
php 여정시작


# 윈도우 환경

## Visual C++ Redistributable for Visual Studio 2015

설치이유 : php 윈도우용이 VC2015로 컴파일 되었기때문에, 런타임에 필요한 구성요소 설치

- http://www.microsoft.com/en-us/download/details.aspx?id=48145

## PHP

- https://windows.php.net/download/
- https://windows.php.net/downloads/releases/php-7.3.5-nts-Win32-VC15-x64.zip

Non Thread Safe Zip 버젼을 받아서 아래와 같이 버젼이 구분될수 있게
압축을 풀어 줍니다. 

    C:/PHP/7.3.5>
    C:/PHP/7.2.0>

### php ini 설정

    php.ini-development -> php.ini 으로 파일명변경
    php.ini 편집
    memory_limit = 256M 을 찾아 1G로 메모리 사용량 높이기(라라벨 기본 요구 메모리 1G)

    php 외부확장 모듈은 dll로 관리가 되며 윈도우용은 ext 경로에서 dll을 확인할수 있습니다.
    기본 모듈 사용을 활성화합니다.

    extension_dir = "ext"    
    extension=php_gd2.dll
    extension=php_curl.dll
    extension=php_mbstring.dll
    extension=php_openssl.dll
    extension=php_pdo_mysql.dll
    extension=php_pdo_sqlite.dll
    extension=php_sockets.dll

    윈도우 환경변수 path를 php.exe가 존재하는 C:/PHP/7.3.5> 경로 추가합니다.

    아무 콘솔 경로에서 php -v 를 하여 원하는 버젼이 표시가 되면 성공
    PS C:\Users\아무개> php -v
    PHP 7.3.5 (cli) (built: Mar 27 2018 15:23:04) ( NTS )
    Copyright (c) 1997-2017 The PHP Group
    Zend Engine v3.0.0, Copyright (c) 1998-2017 Zend Technologies
    
### Composer 설치
-https://getcomposer.org/download/

위 경로에서 Composer-Setup.exe 설치 진행을 하면, php 경로를 자동으로 찾아서
설치및 연동이 가능해집니다.

Composer는 모듈의 의존성을 관리해주는 툴로서 , 닷넷에서는 누겟
자바에서는 메이븐 정도로 생각하면되겠습니다.


## 라라벨 설치
- https://laravel.kr/docs/5.6/installation

    라라벨 전역 설치
    composer global require "laravel/installer"

    프로젝트 템플릿 생성
    laravel new mySite

    프로젝트를 생성하면 league/flysystem을 설치하라는 경고문이 나오게됩니다.
    프로젝트 경로에서 다음을 실행하여 라라벨의 의존 구성패키지를 설치합니다.
    

    mySite>composer require league/flysystem

    php 서버실행
    mySite>php artisan serve


## IDE (VisualStudio Code)
- https://code.visualstudio.com/

설치후 PHP 개발을 위한 다음 Extension 설치
- PHP InteliSense
- Code Runner
- PHP Debug
- HTML CSS Suport

