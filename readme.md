---


---

<h1 id="documentazione-progetto-mentcare"><strong>DOCUMENTAZIONE PROGETTO: MENTCARE</strong></h1>
<h2 id="esame-di-ingegneria-del-software">ESAME DI INGEGNERIA DEL SOFTWARE</h2>
<h3 id="studente-amore-benedetta">Studente: Amore Benedetta</h3>
<h3 id="matricola-vr-445458">Matricola: VR 445458</h3>
<h3 id="studente-frasson-alessia">Studente: Frasson Alessia</h3>
<h3 id="matricola-vr-447848">Matricola: VR 447848</h3>
<h3 id="docente-mariano-ceccato">Docente: Mariano Ceccato</h3>
<h3 id="anno-accademico-20202021">Anno Accademico: 2020/2021</h3>
<h1 id="section"></h1>
<h2 id="indice">INDICE</h2>
<ul>
<li>
<h3 id="requisiti">REQUISITI</h3>
</li>
<li>
<h3 id="scenari">SCENARI</h3>
</li>
<li>
<h3 id="design">DESIGN</h3>
</li>
<li>USE CASE COMPLETO DI TUTTI GLI UTENTI DEL SISTEMA</li>
<li>ACTIVITY PER MEDICO</li>
<li>SEQUENCE DIAGRAM PER CONTROLLER</li>
<li>CLASS DIAGRAM PER LE CLASSI IMPLEMENTATE</li>
<li>
<h3 id="quality-assurance">QUALITY ASSURANCE</h3>
</li>
<li>
<h3 id="scelte-implementative">SCELTE IMPLEMENTATIVE</h3>
</li>
<li>TOOL DI SVILUPPO</li>
</ul>
<h1 id="section-1"></h1>
<h1 id="requisiti-1">REQUISITI</h1>
<p>Siamo di fronte ad un sistema di cliniche che, al fine di garantire la praticità a tutti gli utenti, prevede un’applicazione utilizzabile sia da computer sia da smartphone.<br>
L’applicazione gestisce un database un sistema di cliniche diurne, i pazienti ospitati e visitati e consente diversi privilegi di accesso. Le cliniche in gestione sono sia strutture diurne, come comunità, in cui i pazienti si recano per svolgere attività ricreative, incontrare medici specialisti e ricevere le cure adeguate, sia cliniche ospedaliere.<br>
Le informazioni dei pazienti riguardano i dati personali, le cartelle cliniche, i trattamenti ricevuti, per esempio prescrizione di farmaci o visite mediche. Questi dati sono soggetti al trattamento della privacy, per i quali il tutore o il paziente stesso firmano il modulo di consenso. Inoltre il manager delle cliniche ha il consenso a rilasciare i dati alle forze dell’ordine, per compiere indagini giudiziarie o processi.<br>
Il paziente non ha alcun tipo di interazione con il sistema, perciò è necessario memorizzare il contatto di un parente o tutore, che sarà usato in caso di urgenze o allarmi. Alcuni di questi casi sono:</p>
<ul>
<li>il paziente può compiere azioni pericolose per se stesso o per gli altri</li>
<li>il paziente può perdersi nella clinica</li>
<li>il paziente può dimenticare una visita</li>
<li>il paziente può perdere una prescrizione<br>
In queste situazioni un medico o un infermiere dovrà segnalare l’accaduto tramite un allert nel sistema.<br>
Gli utenti del sistema sono:</li>
<li>staff medico: medici, infermieri e infermieri a domicilio</li>
<li>staff non medico: receptionist, IT e manutentori, amministratore</li>
</ul>
<p>UTILIZZO DA PARTE DEL MEDICO CURANTE<br>
I medici possono accedere al sistema con login tramite username e password, dalla propria area privata visualizzano la lista dei pazienti e possono visualizzare ed aggiornare la cartella clinica di ognuno.<br>
All’interno della cartella possono inserire nuove diagnosi con l’eventuale stato di pericolosità, nuove visite con eventuali prescrizioni (farmacologiche e psicologiche) e possono segnalare situazioni di pericolo (<em>“SEGNALA PROBLEMA URGENTE”</em>).<br>
Possono inoltre vedere e stampare lo storico di ogni paziente.</p>
<p>UTILIZZO DA PARTE DELL’INFERMIERE<br>
Gli infermieri possono accedere al database con login tramite username e password, dalla propria area privata vedono la lista di pazienti e possono aggiornare la cartella clinica di ognuno. Nella cartella devono inserire lo svolgimento delle terapie psicologiche, la somministrazione dei farmaci prescritti e possono segnalare un alert. Inoltre possono vedere e stampare lo storico di ogni paziente.</p>
<p>UTILIZZO DA PARTE DELLA RECEPTIONIST<br>
Le receptionist accedono al sistema con username e password e possono vedere l’agenda di ogni medico, per gestire gli appuntamenti con i pazienti o con i loro familiari.</p>
<p>UTILIZZO DA PARTE DEL MANAGER DELLE CLINICHE<br>
Il manager ha accesso come amministratore e può inserire un nuovo paziente creandone la cartella clinica, in questa fase fa firmare il modulo per il trattamento dei dati personali ed il consenso per fornire informazioni necessarie ad eventuali indagini.<br>
Quando un paziente termina la cura la cartella viene archiviata.<br>
Il manager può visualizzare un report mensile relativo all’andamento economico delle cliniche e al numero di pazienti in terapia.<br>
Nello specifico il report contiene il numero di pazienti in ogni clinica diurna, il numero di pazienti che sono stati registrati e il numero di pazienti che hanno concluso le cure, il numero di pazienti visitati nelle cliniche ospedaliere e, per ogni clinica, il totale del costo dei farmaci prescritti e somministrati, suddivisi in dosi.</p>
<h1 id="section-2"></h1>
<h1 id="scenari-medico">SCENARI (MEDICO)</h1>
<p><em>Si assume che:</em></p>
<ul>
<li>il medico abbia già effettuato il login nel sistema;</li>
<li>il database contenga già tutti i pazienti della clinica inseriti dal personale dedicato a questa attività.</li>
</ul>
<p><strong>Visualizzazione lista pazienti (Homepage)</strong></p>
<ul>
<li>
<p>Situazione iniziale:<br>
Il medico ha appena effettuato il login.</p>
</li>
<li>
<p>Normale utilizzo<br>
Il medico visualizza nella Homepage la lista dei pazienti della clinica.<br>
Per ogni paziente sono indicati: nome, cognome, data di nascita e codice fiscale.<br>
Da questa pagina l’utente ha la possibilità, cliccando sul link <em>Cartella clinica</em> posto accanto ai dati di ogni paziente, di accedere alla cartella clinica del paziente desiderato.</p>
</li>
<li>
<p>Situazione finale<br>
Il sistema mostra al medico la cartella clinica selezionata.</p>
</li>
</ul>
<p><strong>Segnalazione urgenza</strong></p>
<ul>
<li>
<p>Situazione iniziale:<br>
Il medico si ritrova nella condizione di dover segnalare un’urgenza, tra queste possiamo indicare: riscontro di situazione di pericolosità del paziente (per sè stesso e/o per gli altri), ritrovamento di un paziente in stato confusionale nella clinica, necessità di effettuare ai parenti del paziente una segnalazione in merito ad un appuntamento a cui il paziente non si è presentato…</p>
</li>
<li>
<p>Normale utilizzo:<br>
Dopo aver aperto la cartella clinica del paziente il medico può cliccare sul link <em>“SEGNALA PROBLEMA URGENTE”</em> ed ha la possibilità di inserire nel sistema la segnalazione e, nel caso di utilizzo di app mobile, effettuare direttamente una telefonata al contatto di riferimento del paziente.<br>
Dalla pagina il medico può richiedere anche aiuto al personale reperibile che verrà avvisato tramite un alert sul cercapersone.</p>
</li>
<li>
<p>Possibili problemi:<br>
Nel caso in cui, per svariati motivi, il sistema non potesse effettuare la segnalazione correttamente verranno mostrati al medico: un messaggio di errore, il contatto di riferimento del paziente ed il numero telefonico del personale reperibile.</p>
</li>
<li>
<p>Situazione finale:<br>
Dopo aver inserito la segnalazione ed effettuato le telefonate opportune il medico potrà tornare alla cartella clinica del paziente.</p>
</li>
</ul>
<p><strong>Inserimento diagnosi</strong></p>
<ul>
<li>
<p>Situazione iniziale:<br>
Il medico ha diagnosticato una nuova malattia ad un paziente.</p>
</li>
<li>
<p>Normale utilizzo:<br>
Dopo aver aperto la cartella clinica del paziente il medico può cliccare sul link <em>“Inserimento diagnosi”</em>. Il sistema mostra la pagina di inserimento diagnosi nella quale il medico dovrà indicare: nome diagnosi, eventuali note ed un’eventuale pericolosità per il paziente o per gli altri (già pre-impostata a <em>“Non pericoloso”).</em></p>
</li>
<li>
<p>Possibili problemi:<br>
Nel caso in cui il medico non indichi il nome della diagnosi il sistema non effettua alcuna aggiunta, ricarica semplicemente la pagina mostrando in rosso un messaggio di errore ricordando al medico di riempire il campo.</p>
</li>
<li>
<p>Situazione finale:<br>
Il sistema aggiunge la diagnosi al database e mostra al medico la cartella clinica del paziente con la lista aggiornata delle diagnosi.</p>
</li>
</ul>
<p><strong>Inserimento visita e prescrizioni</strong></p>
<ul>
<li>
<p>Situazione iniziale:<br>
Il medico ha visitato un paziente.</p>
</li>
<li>
<p>Normale utilizzo:<br>
Dopo aver aperto la cartella clinica del paziente il medico può cliccare sul link <em>“Nuova visita”</em>. Il sistema mostra la pagina di inserimento visita nella quale il medico può, se desidera, inserire un report della visita.<br>
Cliccando <em>“Invia”</em> la visita viene salvata nel database e viene mostrato al medico il report della visita. Da questa pagina il medico può, cliccando sul link <em>“Nuova prescrizione”</em> effettuare una prescrizione associata alla visita. Ha la possibilità di selezionare un farmaco (non obbligatorio) e di inserire delle note nelle quali indicare la frequenza di assunzione (se prescrizione farmacologica) o la terapia psicologica prescritta.<br>
Confermando la prescrizione si riaprirà il report della visita.</p>
</li>
<li>
<p>Possibili problemi:<br>
Nel caso in cui il medico non compili il campo <em>“note”</em> nella prescrizione il sistema non effettua alcuna aggiunta, ricarica semplicemente la pagina mostrando in rosso un messaggio di errore ricordando al medico di riempire il campo.</p>
</li>
<li>
<p>Situazione finale:<br>
Il sistema aggiunge la visita e le eventuali prescrizioni al database e mostra al medico la cartella clinica del paziente con la lista delle visite aggiornata. Dalla lista delle visite sarà possibile accedere al report di ogni visita.</p>
</li>
</ul>
<p><strong>Stampa cartella clinica</strong></p>
<ul>
<li>
<p>Situazione iniziale:<br>
Il medico desidera stampare la cartella clinica del paziente.</p>
</li>
<li>
<p>Normale utilizzo:<br>
Dopo aver aperto la cartella clinica del paziente il medico può cliccare sul bottone <em>“Stampa questa pagina”</em>. Il sistema avvia la stampa della pagina visualizzata.</p>
</li>
<li>
<p>Possibili problemi:<br>
Funzionalità implementata con <em>Javascript</em>. Nel caso in cui non fosse supportato dal browser il bottone non viene mostrato all’utente.</p>
</li>
<li>
<p>Situazione finale:<br>
Il sistema mostra la finestra per effettuare la stampa della pagina al medico che dovrà solo confermare per avere il documento in formato cartaceo.</p>
</li>
</ul>
<p><strong>PDF report storia clinica</strong></p>
<ul>
<li>
<p>Situazione iniziale:<br>
Il medico desidera generare un PDF contenente il report della storia clinica del paziente.</p>
</li>
<li>
<p>Normale utilizzo:<br>
Dopo aver aperto la cartella clinica del paziente il medico può cliccare sul bottone <em>“PDF Report storia clinica”</em>. Il sistema crea il pdf e permette il salvataggio del documento.</p>
</li>
<li>
<p>Possibili problemi:<br>
Funzionalità implementata con <em>Javascript</em>. Nel caso in cui non fosse supportato dal browser il bottone non viene mostrato all’utente.</p>
</li>
<li>
<p>Situazione finale:<br>
Il sistema mostra la finestra per effettuare il salvataggio del pdf al medico che dovrà solo confermare per avere il documento sempre disponibile sul suo dispositivo.</p>
</li>
</ul>
<h1 id="section-3"></h1>
<h1 id="design-1">DESIGN</h1>
<h2 id="use-case">USE CASE</h2>
<h3 id="medico">MEDICO</h3>
<p>Le attività previste per lo staff medico sono:</p>
<ul>
<li>Accesso al sistema con login e password mediche;</li>
<li>Nella homepage, visualizzare la lista di pazienti;</li>
<li>Dalla homepage, aprire la cartella clinica dei pazienti;</li>
<li>Dalla cartella clinica inserire le diagnosi, le visite effettuate con eventuali terapie prescritte;</li>
<li>Dalla cartella clinica, segnalare un allert nel caso di situazione critica;</li>
<li>Dalla homepage, stampare lo storico di un paziente.<br>
<a href="https://app.genmymodel.com/api/projects/_cTV7QFwOEeul4L4ngN2BiA/diagrams/_cTV7Q1wOEeul4L4ngN2BiA/svg">https://app.genmymodel.com/api/projects/_cTV7QFwOEeul4L4ngN2BiA/diagrams/_cTV7Q1wOEeul4L4ngN2BiA/svg</a></li>
</ul>
<h3 id="infermiere-e-infermiere-a-domicilio">INFERMIERE e INFERMIERE A DOMICILIO</h3>
<p>Le attività previste per gli infermieri sono:</p>
<ul>
<li>Accesso al sistema con login e password sub-mediche;</li>
<li>Nella homepage, visualizzare la lista di pazienti;</li>
<li>Dalla homepage, aprire la cartella clinica dei pazienti;</li>
<li>Dalla cartella clinica inserire le attività svolte e i farmaci somministrati;</li>
<li>Dalla cartella clinica, segnalare un allert nel caso di situazione critica;</li>
<li>Dalla homepage, visualizzare e stampare lo storico di un paziente.<br>
<a href="https://app.genmymodel.com/api/projects/_GgK7IFwUEeul4L4ngN2BiA/diagrams/_GgK7I1wUEeul4L4ngN2BiA/svg">https://app.genmymodel.com/api/projects/_GgK7IFwUEeul4L4ngN2BiA/diagrams/_GgK7I1wUEeul4L4ngN2BiA/svg</a></li>
</ul>
<h3 id="receptionist">RECEPTIONIST</h3>
<p>Le attività previste per le receptionist sono:</p>
<ul>
<li>Accesso al sistema con login e password semplici;</li>
<li>Nella homepage, visualizzare l’agenda di ogni medico;</li>
<li>Inserire un appuntamento con un paziente o con un famigliare/tutore.<br>
<a href="https://app.genmymodel.com/api/projects/_QnSfoFwVEeul4L4ngN2BiA/diagrams/_QnSfo1wVEeul4L4ngN2BiA/svg">https://app.genmymodel.com/api/projects/_QnSfoFwVEeul4L4ngN2BiA/diagrams/_QnSfo1wVEeul4L4ngN2BiA/svg</a></li>
</ul>
<h3 id="manager">MANAGER</h3>
<p>Le attività previste per il manager sono:</p>
<ul>
<li>Accesso al sistema con login e password da amministratore;</li>
<li>Inserire un nuovo paziente e creare una cartella clinica contenente l’anagrafica e il modulo per la privacy;</li>
<li>Archiviare la cartella clinica dei pazienti che concludono il trattamento;</li>
<li>Visualizzare lo storico del paziente ed esportarlo su richiesta;</li>
<li>Visualizzare il report mensile amministrativo ed economico.<br>
<a href="https://app.genmymodel.com/api/projects/_77z5oFwVEeul4L4ngN2BiA/diagrams/_77z5o1wVEeul4L4ngN2BiA/svg">https://app.genmymodel.com/api/projects/_77z5oFwVEeul4L4ngN2BiA/diagrams/_77z5o1wVEeul4L4ngN2BiA/svg</a></li>
</ul>
<h1 id="section-4"></h1>
<h2 id="activity-diagram">ACTIVITY DIAGRAM</h2>
<p><a href="https://app.genmymodel.com/api/projects/_HhIrEFwjEeul4L4ngN2BiA/diagrams/_HhIrFFwjEeul4L4ngN2BiA/svg">https://app.genmymodel.com/api/projects/_HhIrEFwjEeul4L4ngN2BiA/diagrams/_HhIrFFwjEeul4L4ngN2BiA/svg</a></p>
<h1 id="section-5"></h1>
<h2 id="sequence-diagram">SEQUENCE DIAGRAM</h2>
<p><a href="https://app.genmymodel.com/api/projects/_MdrZwFx0Eeul4L4ngN2BiA/diagrams/_MdrZxFx0Eeul4L4ngN2BiA/svg">https://app.genmymodel.com/api/projects/_MdrZwFx0Eeul4L4ngN2BiA/diagrams/_MdrZxFx0Eeul4L4ngN2BiA/svg</a></p>
<h1 id="section-6"></h1>
<h2 id="class-diagram">CLASS DIAGRAM</h2>
<p><a href="https://github.com/AmoreBenedetta/progettoMentcare/blob/main/Starter%20Class%20Diagram%20%282%29.pdf">Link class diagram</a></p>
<h1 id="quality-assurance-1">QUALITY ASSURANCE</h1>
<h2 id="unit-test">UNIT TEST</h2>
<p>Test di unità svolti su ogni classe appartenente al package <em>Models</em>.<br>
Per le classi <em>Diagnosi, Farmaco, Paziente, Prescrizione e Visita</em> sono stati testati tutti i metodi Getter e Setter appartenenti a ciascuna classe.</p>
<p>Per completezza, nonostante queste fossero funzioni implementate dall’interfaccia <em>CrudRepository</em> sono stati testati, per ogni classe appartenente al package <em>Repositories</em>, anche i principali metodi di: inserimento, cancellazione e cancellazione di tutti gli elementi.</p>
<p>La coverage riscontrata dai test sul package <em>Model</em> è del 100%.</p>
<h2 id="acceptance-test">ACCEPTANCE TEST</h2>
<p>Sono state testate tutte le pagine HTML implementate.<br>
Per ciascuna pagina abbiamo testato il click ad ogni link presente e se necessaria la compilazione di form.<br>
Riassumiamo i test implementati:</p>
<p><strong>HOMEPAGE</strong></p>
<ul>
<li>Test Home come prima pagina caricata</li>
<li>Test apertura cartella clinica di un paziente</li>
</ul>
<p><strong>CARTELLA CLINICA</strong></p>
<ul>
<li>Test click link Home</li>
<li>Test apertura pagina inserimento diagnosi</li>
<li>Test apertura pagina inserimento segnalazione</li>
</ul>
<p><strong>NUOVA DIAGNOSI</strong></p>
<ul>
<li>Test inserimento dati corretti</li>
<li>Test invio form senza aver inserito il campo “nome” (obbligatorio)</li>
<li>Test click link Home</li>
<li>Test click link cartella clinica paziente</li>
</ul>
<p><strong>NUOVA VISITA</strong></p>
<ul>
<li>Test inserimento visita</li>
<li>Test click link Home</li>
<li>Test click link cartella clinica paziente</li>
</ul>
<p><strong>NUOVA PRESCRIZIONE</strong></p>
<ul>
<li>Test inserimento dati corretti</li>
<li>Test invio form senza aver inserito il campo “note” (obbligatorio)</li>
<li>Test reset button</li>
<li>Test click link Home</li>
<li>Test click link cartella clinica paziente</li>
</ul>
<p><strong>SCHEDA VISITA</strong></p>
<ul>
<li>Test click link nuova prescrizione</li>
<li>Test open report visita dalla cartella clinica (Link nuova prescrizione non più presente)</li>
<li>Test click link Home</li>
<li>Test click link cartella clinica paziente</li>
</ul>
<h1 id="section-7"></h1>
<h1 id="scelte-implementative-1">SCELTE IMPLEMENTATIVE</h1>
<p>Il patter su cui si basta il nostro progetto è Spring-MVC, in cui il Controller gestisce le azioni che può compiere un medico, una volta loggato; il Model contiene tutte le classi che fanno riferimento ai dati salvati in modo persistente; il View è l’interfaccia con il medico, creata in HTML.<br>
Abbiamo scelto questo pattern strutturale in quanto si adatta alla nostra piattaforma web poichè l’interfaccia può subire continue variazioni a seguito di inserimento e/o modifica di dati.<br>
Inoltre Spring-MVC consente di dividere nettamente la parte di visualizzazione e gestione della base di dati, che può essere modificata in modo indipendente dal resto del sistema.<br>
Abbiamo scelto di implementare per intero la parte di controllo sulle attività che può svolgere il medico, su cui sono stati eseguiti tutti i casi di test.<br>
In questa fase di implementazione non sono stati gestiti il login del medico e la grafica finale del sistema.<br>
Questa versione deve essere vista come una bozza del sistema finale utilizzata per mostrare le varie funzionalità.</p>
<h2 id="tool-di-sviluppo">TOOL DI SVILUPPO</h2>
<p>Per lo sviluppo della nostra applicazione è stato usato il tool IntelliJ, proposto a lezione.<br>
Il codice è stato implementando utilizzando HTML per l’interfaccia Web e Java (sfruttando il framework SpringBoot) per tutto il resto del programma.<br>
Gradle è stato utilizzato per la parte di compilazione del software.<br>
I test di unità sono stati effettuati con JUnit e quelli di accettazione con JWebUnit.<br>
La condivisione finale del progetto è avvenuta su GitHub.<br>
I diagrammi UML sono stati creati con il tool on-line genmymodel e sono stati importati nella documentazione.<br>
Per scrivere la documentazione in formato .md è stato utilizzato il tool on-line stackedit.</p>

