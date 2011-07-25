Huth 5 Modal Logics and agents
===============================

## 5.1 Modes of truth

**Wo ist der Unterschied zur klassischen Logik?**

 - klassische Logik kennt nur eine Wahrheit.



**Welche Arten von Wahrheit gibt es?**

 - Temporal
 - Notwendigerweise Wahr
 - Immer wahr
 - wird als wahr angenommen
 - als wahr bestätigt



**Wofür wird es eingesetzt?**

- Multi agent Systeme



**Wie wird das modelliert?**

- unäre Operatoren BOX und DIAMOND



## 5.2 Basic Modal Logic

**Was macht Basic Modal Logic basic?**

### 5.2.1 Syntax

**Welche Zeichen gibt es?**

- siehe BNF

**BNF?**

Binding pro?

1. unär
2. und / oder
3. folgerung (->)/ doppelfolgerung (<->)


### 5.2.2 Semantik

**Wie ist die Semantik definiert?**

- ein model in multi modal logik ist eine Kripke Struktur bestehend aus:
 - W eine menge von Welten
 - R einer Relation (WxW) die angibt welche Welten von dieser Welt erreicht werden können
 - L eine Funktion L: W -> P(Atome) die definiert welche Atome in dieser Welt vorhanden sind 		 (Wissensbasis)


**Wie wissen wir das etwas eine Wahrheit hat und welche diese Wahrheit ist?**

- Die einzelnen Wahrheiten folgen ihrer Modellierung
- wir wissen das eine formel ø in x€W wahr ist, wenn w ø erfüllt, sprich die Regeln auf S. 310 einhält.


**Was ist die Semantik von Box und Diamond?**

- Box, so eine Art ForEach. Es gilt, wenn die formel ø in allen Welten w' erfüllt wird, die von w erreichbar sind.
- ist von w aus keine Welt erreichbar ist box immer wahr

- Diamond
- besagt es gibt min. eine Welt w' die von w erreichbar ist, die die formel ø erfüllt
- Diamond ist fals, wenn w keine verknüpfungen zu anderen Welten hat.
- ◊ ist == -Box- (lies: die aussage etwas stimmt nicht für alle welten ist falsch)



**Was muss man im Unterschied zur klassischen Logik beachten / wissen?**

- in Propositiional Logik ist ein Model lediglich eine Belegung der Variablen
- kappt bei multi modal nicht, weil mehrere art von Wahr existrieren



**Was ist ein Formel Schema?**

- Eine Formel mit Platzhalten für beliebige weiter Formeln.
- quasi ein Parse Tree mit Platzhaltern
- eine Welt er füllt ein Schema, wenn alle Welten alle Instanzen dieses Schemas erfüllen
- Bsp: Schema -ø ^ µ: alle erfüllen -p ^ q, aber eine welt erfüllt -a ^ q nicht => das schema ist nicht erfüllt, weil -a ^ q auch zu dem schema gehört



**Was unterscheidet ein Schema von einer Formel?**

- eine formel beinhaltet Atome



**Wann folgt eine formel ø semantisch aus einer Menge von Formeln ∏?**

- Wenn es in einem der Modelle M mit ∏ eine welt x gibt aus der ø folgt immer dann wenn aus x auch alle elemente aus ∏ folgen.



**Wann sind 2 Formeln ø und π in multi modal logik equvivalent?**

- immer wenn aus ø ||- π (aus ø folgt semantisch π) UND π ||- ø
- die def is die selbe wir in Propositionallogick, nur ist die semantik anders definiert


**Wann ist eine Formel ø valide?**

- wenn ||= ø gilt (wenn aus allen Welten in allen Modellen ø folgt)



**Was bringt uns das?**

- Formeln können generell ersetzt werden ohne sich Gedanken machen zu müssen ob sie in diesem Modell angewendet werden können.




## 5.3 Logic Engineering

**Was ist das?**

- LE ist das Handwerk eine Modal Logick zu erstellen die die gewünschte Form der Wahrheit modelliert
- zur Erinnerung Wahrheitsformen sind z.B. Wissen, Glauben, Immer Wahr, zwangsläufig war



**Wie funktioniert das?**

- Die Wahrheitsform wird im Operator Box modeliert
- daraus ergibt sich eine leseweise für den Operator ◊ (◊ == -Box-)
- valide Formeln spielen eine Rolle
- Nur K: Box(ø->π) -> (Box(ø) -> Box(π)) ist valide in Basic Modal Logic
- es gibt andere Formel-Schemata die im Alg. nicht valide sind:
 - Siehe Huth S. 317
- Hauptaufgabe ist jetzt sich zu überlegen welche Formel-Schemata für die gewünschte Form der Wahrheit valide sein sollen und diese entsprechend zu modellieren


**Was bringt das?**


### 5.3.3 Correcpondence theory

**Was besagt die Correspondence theory?**

- Die Theorie stellt einen Zusammenhang zwischen den Eigenschaften der R Relation R:(WxW) z.B. Transitivität und der Validität von bestimmten Formeln z.B.: Box(ø) -> ø her



**Was kann man daraus ableiten?**

- er ermöglicht aus R abzulesen welche Formeln valide sind und vise versa


**Wie steht sie im Zusammengang mit dem bisher gelernten?**

- daraus ergeben sich die Möglichkeit sich der Logik aus zwei Richtungen zu nähern und dies so besser / einfacher gestallten / kontrollieren zu können



## 5.4 Natural Deduction (natürliche Folgerung)

**Wozu ist das gut?**

Zum validieren von Aussagen in Modal Logik.
Validieren heißt nach einem Kalkukus etwas für den allgemeinen Fall nachzuweisen und seine Gültigkeit zu zeigen.



**Wie funktioniert das?**

Neben den Boxen die wir aus der Aussagenlogik kennen (für annahmen usw. ) kommen neue Boxen dazu. Diese werden gestrichelt dargestellt haben aber eine andere Aussage. Sie ermöglichen das Folgern in einer unbestimmten, aber erreichbaren Welt.

die regeln sind []i und []e .

mit []e kann man eröffnet man so eine Box in der man Folgerungen in einer unbestimmten verbundenen Welt führen kann. aus []ø wird dann ø.

beim verlassen einer gestrichelten Box kommt []i zum Einsatz. Es macht aus ø: []ø


**Was ist zu beachten?**

- Man kann nur formeln nach dem Schema []ø in eine gestrichelte Box aufnehmen.
- Wenn man eine Formel aus einer gestrichelten Box rauszieht kommt ein [] dazu.

- für stärkere Logiken z.B. KT45 gibt es extra regeln für T 4 und 5 die das Folgern entsprechend anpassen.



## 5.5 Reasoning about knowlage in Multi-agent systems

**Vorraussetzungen?**


**Einsatzgebiete?**

- Spiele, 
- Wirtschaft
- Protokolle
- Kryptographie


**Wie formuliert man ein Problem in MMLogic?**

**Wie funktioniert die Berechnung?**

**Limits?**


## KT45n

**What is it?**
generalisation of modalities. Instead of one knowlage there are i Agends, of wich each has its own knowlage written as K_i_ . So K_1_ø means Agent 1 knows ø.

Based on this the is the need for further descriptions. E_G_ø means everyone in the Group G knows ø. for G = {1,2,3} Gø == K_1_ø ^ K_2_ø ^ K_3_ø

__Attention__ Something can be wider knows as E_G_ø (with G including all agents). Namely E_G_E_G_ø, which means that everyone know that everyone knows ø. Also E_G_E_G_E_G_ø is wider knows as E_G_E_G_ø , and so forth. 

Because this may extent to infinity but the logic is bound to be finit. There is the notation of C_G_ø thats described not by its equvialence but by its semantics.

Lastly there is the concept of D_G_ø . This means there is some knowlage ø, thats distributes amoung the Group G, while no one knows about it everybody could know about it if they put their heads together.

**Differenze to KT45**

This logic is greater in a sense that it includes more than 1 knowlage. Namely a knowlage for each Agent.


**Why needed?**

**How to apply**






