# git-log
GIT Log oneliner

Colored format
    
    git log --graph --pretty=format:"%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset" --abbrev-commit

One line per file with PHP
    
    git log --pretty="%ci;%h;%s" --name-only --since '2020-04-01' --until '2021-03-31'|php -r "    \$date = '';    while(\$line=fgets(STDIN)) {     \$line = trim(\$line, \"\r\n \");     if(preg_match('/\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.*\$/', \$line)) {      \$date = \$line; continue;     } if(!empty(\$line)) echo trim(\$date, \"\n\").''.\$line.\"\n\";    };"`

