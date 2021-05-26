# my_bashrc
my (OVelychko) bashrc config file for the Ubuntu OS

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
