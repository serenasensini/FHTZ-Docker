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

Il Dockerfile è essenzialmente le istruzioni di compilazione per costruire l'immagine. Docker utilizza questo file per creare l'immagine stessa. Un esempio di Dockerfile è il seguente:

```
FROM ubuntu:18.04
COPY . /app
RUN apt update && apt upgrade
CMD python /app/app.py
```

Analizzando le istruzioni, possiamo vedere che:
- FROM : utilizza un'immagine base che possa fornirci uno strumento con cui far partire il nostro sistema; in questo caso, si è scelto Ubuntu come sistema operativo, perché ha già Python installato, ma è possibile utilizzare moltissime altre immagini, disponibili sul Docker Hub;
- COPY : copia la cartella corrente, indicata con '.', nella cartella '/app' del container;
- RUN : esegue dei comandi da terminale; in questo caso, aggiorna il sistema;
- CMD : esegue lo script Python, in questo caso, ma può essere utilizzato per molti altri scopi.

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
- Differenza tra RUN, CMD e ENTRYPOINT? RUN esegue i comandi in un nuovo livello e crea una nuova immagine. Ad esempio, è spesso usato per installare pacchetti software; viene creata un'immagine intermedia che poi viene scartata una volta terminata l'esecuzione dell'attività richiesta; CMD imposta il comando e/o i parametri predefiniti, che possono essere sovrascritti dalla riga di comando quando viene eseguito il contenitore; ENTRYPOINT configura un contenitore che verrà eseguito come un eseguibile. La differenza principale tra l’istruzione ENTRYPOINT e le istruzioni RUN è il momento della loro esecuzione: le istruzioni specificate da RUN vengono eseguite __durante__ la costruzione di un’immagine, mentre l’istruzione specificata da ENTRYPOINT verrà eseguita dai contenitori creati __a partire dall’immagine__. Per maggiori dettagli, leggi [qui](http://goinbigdata.com/docker-run-vs-cmd-vs-entrypoint/)
