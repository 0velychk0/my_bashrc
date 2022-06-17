# my_bashrc
my (OVelychko) bashrc config file for the Ubuntu OS

## set bash prompt color
    autoload -U colors && colors
    export PS1="%F{214}%m:%F{lightgreen}%~ "

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
    
