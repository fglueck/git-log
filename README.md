# git-log
## GIT Log OneLiner

### Colored format
#### relative time
    
    git log --graph --pretty=format:"%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset" --abbrev-commit
#### timestamp
    git log --graph --pretty=format:"%C(bold red)%h%Creset -%C(yellow)%d%Creset %s %C(bold green)(%ci) %C(bold blue)<%an>%Creset" --abbrev-commit
    
#### custom timestamp / without graph
    git log  --date="format:%Y-%m-%d %H:%M:%S" --pretty=format:"%C(bold green)%cd: %C(bold red)%h%Creset -%C(yellow)%d%Creset %s %C(bold blue)<%an>%Creset" --abbrev-commit

### One line per file with PHP
    
    git log --pretty="%ci;%h;%s" --name-only --since '2020-04-01' --until '2021-03-31'|php -r "    \$date = '';    while(\$line=fgets(STDIN)) {     \$line = trim(\$line, \"\r\n \");     if(preg_match('/\d{4}-\d{2}-\d{2} \d{2}:\d{2}:\d{2}.*\$/', \$line)) {      \$date = \$line; continue;     } if(!empty(\$line)) echo trim(\$date, \"\n\").''.\$line.\"\n\";    };"`

