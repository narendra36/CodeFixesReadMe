# CodeFixesReadMe
Readme only file with code, OS, app, etc. related fixes

2019 Sep 16
-Application fix for brew/curl
   --the error :: 

      Mac: ~ $ brew cask install -v mactex
      Updating Homebrew...
      ==> Satisfying dependencies
      ==> Installing Formula dependencies: ghostscript
      ==> Installing ghostscript
      ==> Downloading https://homebrew.bintray.com/bottles/ghostscript-9.27_1.mojave.bottle.tar.gz
      /usr/bin/curl -q --show-error --user-agent Homebrew/2.1.11\ \(Macintosh\;\ Intel\ Mac\ OS\ X\ 10.14.6\)\ curl/7.54.0    --fail --location --remote-time --continue-at 0 --output /Users/mparis/Library/Caches/Homebrew/downloads/20e647446b1df8cbb7fbfe3d6731344bba4926797d94e0ccd13d7c67e413e9fa--ghostscript-9.27_1.mojave.bottle.tar.gz.incomplete https://homebrew.bintray.com/bottles/ghostscript-9.27_1.mojave.bottle.tar.gz
        % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                       Dload  Upload   Total   Spent    Left  Speed
        0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
      curl: (35) error:1400410B:SSL routines:CONNECT_CR_SRVR_HELLO:wrong version number
      Error: Failed to download resource "ghostscript"
   
   --solution: step 1
     \$ git config --global http.proxy http://proxyout.lanl.gov:8080
   --solution: step 2
     \$ export HOMEBREW_CURLRC=1 [later put into .bashrc]
