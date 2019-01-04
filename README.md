# Docker essentials

## Cos'è

Il software Docker è una tecnologia di containerizzazione che consente la creazione e l'utilizzo dei container Linux. La tecnologia Docker utilizza il kernel di Linux e le sue funzionalità per isolare i processi in modo da poterli eseguire in maniera indipendente. L'obiettivo dei container è quello di essere indipendenti: la capacità di eseguire più processi e applicazioni in modo separato per sfruttare al meglio l'architettura esistente, ma comunque conservando il livello di sicurezza che sarebbe garantito usando sistemi separati.

## Come installarlo: [Windows](https://docs.docker.com/docker-for-windows/install/)

## Come installarlo: [Linux](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

## Come installarlo: [MacOS](https://docs.docker.com/docker-for-mac/install/)

## Terminologia

### Cos'è un'immagine

Un'immagine Docker è un file utilizzato per eseguire il codice in un contenitore Docker. Un'immagine è essenzialmente costruita dalle istruzioni per una versione completa ed eseguibile di un'applicazione, che si basa sul kernel del sistema operativo host.

### Cos'è un container

I contenitori sono un'astrazione a livello applicativo che raggruppa il codice e le dipendenze. Più contenitori possono essere eseguiti sulla stessa macchina e condividere il kernel del sistema operativo con altri contenitori, ognuno eseguito come processo isolato. I contenitori occupano meno spazio delle macchine virtuali (le immagini dei container hanno in genere decine di MB di dimensioni). In altre parole, i container sono l'istanza di un'immagine.

### Cos'è il Dockerfile

## Comandi

### Comando: ps

Mostra tutti i container attivi. Con l'opzione `-a` si hanno anche i container stoppati.

Esempio:

` docker ps ` 

### Comando: stop

### Comando: build

### Comando: run 

### Comando: exec

### Comando: stop

### Comando: rm

## Tips
- Differenza tra immagine e container? Un'istanza di un'immagine è chiamata contenitore. Hai un'immagine, che è un insieme di livelli che descrivi. Se si avvia questa immagine, si dispone di un contenitore in esecuzione di questa immagine. Puoi avere molti contenitori in esecuzione della stessa immagine.
- Qual è la differenza con una VM? Le macchine virtuali (VM) sono un'astrazione dell'hardware fisico che trasforma un server in molti server. L'hypervisor consente a più macchine virtuali di essere eseguite su una singola macchina. Ogni VM include una copia completa di un sistema operativo, l'applicazione, i binari e le librerie necessarie, occupando decine di GB. Le macchine virtuali sono generalmente lente da avviare. ![Schema](http://img.scoop.it/tImVj_1Pbqv0HJDyMWTmBbnTzqrqzN7Y9aBZTaXoQ8Q=) Credits to: [Blog Docker](https://blog.docker.com/2016/04/containers-and-vms-together/)
