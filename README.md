Repoer som skal forkes finnes her:
https://github.com/AnonymEksamen/exam-app

https://github.com/AnonymEksamen/exam-infra

Naviger deg til credentials_example.yml i exam-infra repoet sin rotfolder. 
Legg inn egne hemmeligheter og gjør om navn til credentials.yml.

Kjør 
``` sh
$ docker-compose up -d
```
deretter
``` sh
$ fly -t <din target> sp  -p <din pipeline> -c concourse/pipeline.yml -l credentials.yml
```
Du må muligens logge deg inn. Url for innlogging gis i terminal.
Svar “y” på “apply configuration”
Kjør
``` sh
$ fly -t <din target> unpause-pipeline -p <din pipeline>
```
Naviger deg til pipeline url oppgitt i terminal
Klikk deg inn på infra jobben og kjør den.
Dette vil trigge deploy jobben til å kjøre etter infra er ferdig og du kan nå pushe til github sin master i exam-app repoet og deploy jobben vil automatisk starte og oppdatere heroku applikasjonen.
