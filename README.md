# my_bashrc
my (OVelychko) bashrc config file for the Ubuntu OS

## set bash prompt color
    autoload -U colors && colors
    export PS1="%F{214}%m:%F{lightgreen}%~ $ "
    export RPROMPT='%F{yellow}%T'

## macos remove java 
    sudo rm -rf /Library/Java/*
    sudo rm -rf /Library/PreferencePanes/Java*
    sudo rm -rf /Library/Internet\ Plug-Ins/Java*

## macos list of java versions
    /usr/libexec/java_home -V

## select java-11 as current
    function set-java-11 {
        sudo update-alternatives --set java /usr/lib/jvm/java-11-openjdk-amd64/bin/java
        export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
    }

## select java-16 as current
    function set-java-16 {
        sudo update-alternatives --set java /usr/lib/jvm/java-16-oracle/bin/java
        export JAVA_HOME=/usr/lib/jvm/java-16-oracle
    }

## clear Idea 30d-trial period
    function clear-idea-eval {
        rm  /home/ovelychko/.config/JetBrains/IntelliJIdea2020.3/options/other.xml
        rm -rf /home/ovelychko/.config/JetBrains/IntelliJIdea2020.3/eval/*
        rm -rf .java/.userPrefs
    }

## Change Apache-Tomcat version from shell 

    function set-tomcat-8 {
        $CATALINA_BASE/bin/shutdown.sh &>/dev/null
        export CATALINA_BASE=~/Apache-Tomcat/apache-tomcat-8.5.71
        export CATALINA_HOME=$CATALINA_BASE
        export CATALINA_TMPDIR=$CATALINA_BASE/temp
        echo 'CATALINA_BASE = ' $CATALINA_BASE
    }

    function set-tomcat-9 {
        $CATALINA_BASE/bin/shutdown.sh &>/dev/null
        export CATALINA_BASE=~/Apache-Tomcat/apache-tomcat-9.0.53
        export CATALINA_HOME=$CATALINA_BASE
        export CATALINA_TMPDIR=$CATALINA_BASE/temp
        echo 'CATALINA_BASE = ' $CATALINA_BASE
    }

    function set-tomcat-10 {
        $CATALINA_BASE/bin/shutdown.sh &>/dev/null
        export CATALINA_BASE=~/Apache-Tomcat/apache-tomcat-10.0.11
        export CATALINA_HOME=$CATALINA_BASE
        export CATALINA_TMPDIR=$CATALINA_BASE/temp
        echo 'CATALINA_BASE = ' $CATALINA_BASE
    }
    
    
## Github commands

Create new branch
    
    $ git branch ovelychko-ME-5469

Get list of branches

    $ git branch -a  

Switch to a nanother branch 

    $ git checkout ovelychko-ME-5469 

Stage file for uploading

    $ git add <file>

Set name to a change

    $ git commit -m "ME-5469 - Fix Spring4Shell ZERO-day exploit CVE-2022-22950 vulnerability" 

Get status

    $ git status 

Upload changed files to server

    $ git push origin ovelychko-ME-5469
    
Update file App.java file from master
    
    $ git checkout master path-to-file
    $ git restore -s origin/master path-to-file

Remove branch locally

    $ git branch -D local_branch

## Run codenarc analysis for Groovy project

    $ git clone https://gitlab.suntechinnovation.com/clover/clover-ui.git
    $ cd clover
    $ docker run --rm -v `pwd`:/ws --user `id -u`:`id -g` codenarc/codenarc:3.3.0-groovy-4.0 -rulesetfiles=file:config/codenarc/rules.groovy
    $ cat CodeNarcReport.html
