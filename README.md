# ADiVuS
Active Directory Vulnerable System

# ADiVuS - Active Directory Vulnerable Systems

ADiVuS è un laboratorio costituito da 3 macchine virtuali in ambiente Active Directory, progettato per riprodurre uno scenario reale di un dominio con vulnerabilità. Il laboratorio comprende due domain controller e un client, creati intenzionalmente con misconfigurazioni al fine di fornire una comprensione degli attacchi che possono verificarsi a causa di tali errori di configurazione.

## Scopo del laboratorio

Il principale obiettivo di ADiVuS è fornire una conoscenza pratica degli attacchi che possono essere sfruttati nel contesto di un ambiente Active Directory. Attraverso la riproduzione di vulnerabilità intenzionali, gli utenti possono acquisire familiarità con gli strumenti di attacco utilizzati dagli hacker e imparare a mitigare tali minacce.

Se si opta per la configurazione dell'ambiente da zero, seguendo le procedure fornite, gli utenti saranno in grado di familiarizzare con i comuni errori commessi durante la configurazione di un domain controller. Ciò permetterà loro di sviluppare la consapevolezza necessaria per prevenire tali incidenti e acquisire la competenza per creare correttamente le policy di gruppo senza incorrere in tali errori.

## Funzionalità del laboratorio

- **Due domain controller**: Il laboratorio comprende due macchine virtuali configurate come domain controller. Questi server simulano un ambiente Active Directory in cui possono verificarsi misconfigurazioni e vulnerabilità.

- **Un client**: Una macchina virtuale è configurata come client e può essere utilizzata per testare gli attacchi al dominio e studiarne le conseguenze.

## Configurazione del laboratorio

Il laboratorio ADiVuS può essere configurato in due modi:

1. **Configurazione manuale**: Puoi seguire le procedure fornite nel repository per creare il laboratorio da zero. Le istruzioni passo-passo ti guideranno attraverso il processo di configurazione delle macchine virtuali e delle vulnerabilità intenzionali.

2. **Scarica il laboratorio pre-configurato**: Se preferisci risparmiare tempo, puoi scaricare il laboratorio già configurato dal link bit.ly/3qfIUUF. In questo caso, sarai in grado di avviare il laboratorio immediatamente senza dover eseguire la configurazione manuale, ma semplicemente importando le macchine in un software di virtualizzazione. È consigliato l'uso di VMware. Inoltre nel caso in cui gli indirizzi di rete sono diversi, dovrai cambiare ed adattare le configurazioni di rete in base alle tue esigenze.

3. **Requisiti funzionali**: Tutte e tre le macchine appartenenti ad Active Directory sono costituite dai requisiti minimi di:
  * 2 core
  * 2 GB di RAM
  * 60 GB di spazio di archiviazione
È possibile adattare le caratteristiche delle macchine in base alla disponibilità dell'hardware utilizzato. Si consiglia l'esecuzione delle tre macchine destinate all'ambiente Active Directory in un host separato per la macchina utilizzata per l'attacco.
È consigliato usare Kali Linux per attaccare l'ambiente in quanto dispone di molti strumenti utilizzati per l'attacco già preinstallati.

Certamente! Ecco una sezione aggiuntiva che elenca gli attacchi possibili nel tuo laboratorio ADiVuS:

## ADiVuS presenta delle vulnerabilità al fine di ricreare un ambiente il più simile possibile alla realtà, in cui simulare frequenti attacchi aziendali:

1. **Scansione della rete con nmap**: Utilizzando lo strumento nmap, è possibile eseguire una scansione della rete per individuare i dispositivi e le porte aperte nel dominio.

2. **Attacco di un servizio web con Metasploit**: Utilizzando Metasploit, è possibile eseguire un attacco a un servizio web vulnerabile nel dominio per sfruttare le falle di sicurezza e ottenere accesso non autorizzato.

3. **Enumerazione di un utente non appartenente al dominio**: Attraverso l'enumerazione, è possibile ottenere informazioni sugli utenti sia all'interno che al di fuori del dominio, al fine di individuare possibili vulnerabilità o scoprire informazioni sensibili.

4. **AS_REP roasting con Impacket**: Con lo sciript GetNPUsers.py di Impacket, è possibile eseguire un attacco di AS_REP roasting per ottenere i ticket di autenticazione di un utente non privilegiato e tentare di decifrarli successivamente.

5. **Decifrazione di un TGT con John The Ripper**: Utilizzando John The Ripper, è possibile tentare di decifrare un Ticket-Granting Ticket (TGT) ottenuto precedentemente per ottenere le credenziali dell'utente associato.

6. **Connessione a un account di dominio tramite RDP**: Attraverso la connessione Desktop remoto (RDP), è possibile accedere a un account di dominio per ottenere il controllo remoto del sistema.

7. **Enumerazione del dominio tramite BloodHound**: Utilizzando BloodHound, è possibile eseguire una scansione del dominio per identificare i privilegi, le relazioni tra gli account e le possibili vie di attacco.

8. **Kerberoasting con Impacket**: Con lo script GetUserSPNs.py di Impacket, è possibile eseguire un attacco di Kerberoasting per ottenere il Ticket Granting Service (TGS) e tentare di decifrarli.

9. **Decifrazione di un TGS con John The Ripper**: Utilizzando John The Ripper, è possibile tentare di decifrare un Ticket-Granting Service (TGS) ottenuto precedentemente per ottenere le credenziali dell'utente associato.

10. **Connessione con evil-winRM al domain controller con un utente appartenente al gruppo degli operatori di backup**: Utilizzando evil-winRM, è possibile connettersi al domain controller utilizzando un utente che appartiene al gruppo degli operatori di backup, ottenendo così un accesso privilegiato.

11. **Abuso di shadow copy**: Sfruttando la copia shadow (shadow copy) del file system, è possibile creare una copia dei file di sistema.

12. **Analisi del file di sistema ntds.dit e del ramo /HKLM/SYSTEM tramite Impacket**: Utilizzando Impacket, è possibile analizzare il file di sistema ntds.dit, che contiene i dati di Active Directory, e il ramo /HKLM/SYSTEM per ottenere gli NTLM hash degli utenti ed informazioni sensibili.

13. **Pass The Hash tramite evil-winRM**: Utilizzando evil-winRM, è possibile eseguire un attacco di "Pass the Hash" utilizzando l'hash della password per ottenere l'accesso ai sistemi senza la necessità di conoscere la password in chiaro.

---

**Nota:** ADiVuS è stato creato unicamente a scopo informativo. Si consiglia di utilizzare il laboratorio solo per attività di studio, ricerca e comprensione delle minacce informatiche. Non è consentito utilizzare il laboratorio per scopi illegali o dannosi.
