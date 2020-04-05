# avansMarkdown
# Portfolio opdr Sjoerd Jakobs
## Reflectie week 2
De groep heeft overlegd over wat we gaan doen en we hebben voor de school simulatie gekozen. Dit had geen grootte reden of goal maar leek ons wel grappig om te doen. Aan het begin van het project heb ik duidelijk gemaakt dat ik al een setup voor het project had. Ik had een super klein framework al gemaakt wat zou kunnen helpen met het project. Als je alleen het minimale gebruikt van het framework komt het op 2 classes uit. Deze classes helpen met een goede structuur behouden voor het project. Ik heb de hele groep gevraagd om dat even door te nemen zodat we het makkelijker kunnen gebruiken en als ze het niet eens zijn met het gebruik ervan dat ze me ook even uitleggen waarom. Naast dat ik graag wilde weten of er iets mis mee was voor hun moesten we ook een andere setup maken als mijne niet genomen werd. Geen van beide werd gedaan, er werd stilletjes geaccepteerd dat we verder gingen met m’n framework. Hoewel dit later nog problemen zou geven was er op dat moment geen reden om te stoppen. Omdat er verder gewerkt werd met het framework heb ik de eerste tijd gekeken hoe ik de 2d graphics window creation kon laten werken met m’n framework. Ik had nog nooit met deze library gewerkt en het was dus even inkomen. De eerste paar dagen waren voor mij besteed aan het maken van een game loop met mijn framework en de animatie loop de je geforceerd op je krijgt van de library. Nadat ik een versie werkend had, wat een scherm gevuld met draaiende blokjes gaf was ik klaar om het aan de rest van de groep te geven. Ik had meerdere voorbeeld classes gemaakt om te helpen met uitleggen hoe het framework werkt. Dingen zoals een voorbeeld student en hoe je die zou kunnen maken. Ik had ook een paar andere voorbeelden om de andere op weg te helpen.
 
## Vakinhoudelijke reflectie:
Wat is de situatie (context)?
Het project is begonnen, we hebben een keuze gemaakt welk soort project we gaan maken en we moeten gaan verzinnen hoe we het gaan opzetten. In het kort, we moeten de basisstructuur bepalen. Hoe gaan we onze programma loop indelen en hoe houden we overzicht.

Welke keuzemogelijkheden heb je?
We hebben een paar keuzes, 
•	Maak alles in de main loop. Dit is een beetje een joke keuze sinds dat heel slecht zou zijn voor het project maar het is technisch gezien een keuze.
•	Laat de andere zelf een klein framework met updateables maken. Deze keuze is prima als ze niet een slechtere versie maken van mijn framework terwijl ze zeggen dat mijn framework niet goed is. Als je een slechtere kopie van iets gaat maken wat er al is zonder reden zie ik niet het nut ervan.
•	Gebruik mijn updateables(standardobjects) framework wat al werkt en ik in een korte tijd kan maken. Dit lijkt mij de beste keuze en daarom heb ik deze keuze ook voorgedragen.

Welke keuze heb je gemaakt?
Keuze 3, mijn framework.

Waarom heb je deze keuze gemaakt?
Omdat mijn framework de mogelijkheid geeft om alles als losse objecten te hebben met hun eigen logic loops in een vaste volgorde. Een object heeft een loop voor input, logic en rendering. Daarnaast heeft het ook extra functies die het object in een inactieve staat zou kunnen houden. Het framework was zeer geschikt voor een simulatie opdracht.
     * happens at: when this object is made
     * how often: once
     * execution order: 0
     */
    protected ExampleObject(FrameworkProgram frameworkProgram) {
        super(frameworkProgram);
    }

    /**
     * happens at: when this object is made
     * how often: once
     * execution order: 0
     */
    public ExampleObject(FrameworkProgram frameworkProgram, boolean usesInput, boolean usesMain, boolean usesRenderer, boolean startsActivated) {
        super(frameworkProgram, usesInput, usesMain, usesRenderer, startsActivated);

        System.out.println("lowest");
    }

    /**
     * happens at: when this object is made
     * how often: once
     * execution order: 1
     */
    @Override
    protected void Start() {
        super.Start();
        //load my shit
    }

    /**
     * happens at: when this object is set to awake, if the object gets created in a awake state it gets called too
     * how often: once
     * execution order: 2
     */
    @Override
    protected void Awake() {
        super.Awake();
    }

    /**
     * happens at: if the object is created to have an input loop
     * how often: every program loop
     * execution order: 3
     * recieves: deltatime          the time inbetween frames
     */
    @Override
    protected void InputLoop(double deltaTime) {
        super.InputLoop(deltaTime);
    }

    /**
     * happens at: if the object is created to have an main loop
     * how often: every program loop
     * execution order: 4
     * recieves: deltatime          the time inbetween frames
     */
    @Override
    protected void MainLoop(double deltaTime) {
        super.MainLoop(deltaTime);
    }

    /**
     * happens at: if the object is created to have an render loop
     * how often: every program loop
     * execution order: 5
     * recieves: deltatime          the time inbetween frames
     */
    @Override
    protected void RenderLoop(double deltaTime) {
        super.RenderLoop(deltaTime);
    }

    /**
     * happens at: when this object is set to sleep, if the object gets created in a sleep state it does not get called
     * how often: once
     * execution order: 6
     */
    @Override
    protected void Sleep()
    {
        super.Sleep();
    }

    /**
     * happens at: when this object is set to be destroyed
     * how often: once
     * execution order: 7
     */
    @Override
    protected void Destroy() {
        super.Destroy();
    }
dit zijn de voorbeeld functies in ExampleObject.java
een van mn voorbeeld classes

 
##Reflectie week3

In deze week was ik vooral aan het meehelpen met het voorbereiden van dingen, er waren 2 versie voor de agenda en beide waren bijna compleet in de main gemaakt. Ik probeerde degene die wel met het framework wilde werken te helpen met uitleg en extra ondersteuning met wat ze bezig waren. Tijdens deze tijd werd het wel al duidelijk dat 2 mensen in de groep niet helemaal blij waren met het framework. Ik heb ook gekeken naar TILE, het programma dat we gebruiken voor het maken van een map. Je krijgt een makkelijke editor om een map te tekenen die dat naar een json file schrijft die je in je programma kan uitlezen. Na een tijdje er mee te werken ben ik andere met hun opdrachten gaan helpen en heeft Timo, die ook bezig was met TILE, het inladen van de map overgenomen. Op dit moment was ik ook betrokken met wat voor classes we nodig hadden om alles op te slaan. Alles wat opgeslagen moet worden wordt in aparte data classes gezet die daarna makkelijk weg geschreven kan worden.


 
##Reflectie week 4
Deze week was ik bezig met het opslaan en inladen van onze data. We hadden al een werkende agenda maar het opslaan van dingen moest nog gebeuren. Dit gebeurde rond dezelfde tijd dat ogp2 uitleg gaf over het opslaan van classes door de classes serializable te laten implementen. Dit heb ik ook gebruikt voor het opslaan en het uitlezen van de data die we hebben. Voor deze week is dit vooral mijn taak geweest. Tijdens deze week hebben we een lang gesprek met onze tutor gehad over dat we het niet eens waren over het framework. We hebben hier lang over gediscussieerd zonder een concrete uitkomst. Onze tutor wilde dat we het uit zoude praten en dat ik een uitleg/pitch voor m’n framework zou maken zodat iedereen het begrijpt. Helaas kon ik dit maar kort doen tot we besloten dat het beter was om op het moment verder te werken aan onze taken. Aangezien ik niet mensen ga forceren om naar me te luisteren had ik daarmee ingestemt. Hierdoor waren we het wel nog steeds niet eens en hebben we dit de week erna alsnog moeten aanpakken. Desondanks dat er op dit moment haperingen waren in ons proces heb ik een degelijk save en load systeem opgezet die naar 1 keer schrijven niet maar aangeraakt hoefde te worden.



 
##Vakinhoudelijke reflectie:
Wat is de situatie (context)?
Ik heb de opdracht gekregen om de code voor het inladen en opslaan van onze data te maken. Hier was al voorheen deels over na gedacht en daar is uitgekomen dat bijvoorbeeld een leraar class een class genaamd leraarData in zich heeft. Alle variabele die opgeslagen moeten worden zetten we in een dataclass zodat we dat makkelijk serializable kunnen maken en wegschrijven. Dit is per klasse niet zo moeilijk, het lastige komt erbij wanneer je niet weet hoeveel je moet opslaan of hoeveel je moet inladen. Naast dat probleem was het ook de vraag hoe ik het gebruiksvriendelijk zou maken voor de rest van de groep. Uiteindelijk heb ik ervoor gekozen om een centrale class te gebruiken waar alles wordt opgeslagen en uitgelezen.

Welke keuzemogelijkheden heb je?
We hebben een paar keuzes voor 2 vragen,
1. Hoe ga je meerdere dingen opslaan van een ongekende grootte/hoeveelheid?
•	Maak een maximumaantal plekken en stop wanneer je dat aantal hebt bereikt, dit limiteert je in hoeveel je kan opslaan.
•	Programeer het opslaan en uitlezen op zo’n manier dat het een unlimited aantal dingen kan opslaan en uitlezen, dit gaat meer tijd kosten.
2. Hoe ga ik het gebruiksvriendelijk/bereikbaar maken? 
•	Maak het zo dat het save/load systeem makkelijk aangeroepen kan worden en mensen stukje voor stukje hun dingen kunnen wegschrijven, als dit niet goed gebruikt wordt kan het moeilijk worden om overzicht te houden.
•	Maak het zo dat alles naar een class wordt weggeschreven die vervolgens gebruikt word om dingen op te slaan en uit te lezen.

Welke keuze heb je gemaakt?
Voor vraag 1 keuze 2, een unlimited aantal dingen.
Voor vraag 2 keuze 2, alles data classes worden neergezet in een class waar het save/load alles ophaalt en neerzet.

Waarom heb je deze keuze gemaakt?
Voor vraag 1:
Ik heb hiervoor gekozen omdat ik ervan overtuigt was dat ik dit gewoon kon, ik moest alleen even bedenken hoe ik het ging doen. De manier waarop ik uit ben gekomen is om alle data classes in arraylists te zetten en dan die arraylists opslaan of vullen met geladen data. Omdat ik niet wist hoeveel dingen erin zouden zitten heb ik ervoor gezorgd altijd het opslaan van een file te eindigen door het opslaan van een object dat null is. Op deze manier kan het programma zien wanneer het klaar is met inladen en hoeft het opslaan alleen ervoor te zorgen dat het eindigt met een object dat null is.

 	package MainPackage.ReadWriteData;
    
    import Data.Rooms.ClassRoom;
    import MainPackage.ReadWriteData.DataClasses.GroupData;
    import MainPackage.ReadWriteData.DataClasses.LessonData;
    import MainPackage.ReadWriteData.DataClasses.StudentData;
    import MainPackage.ReadWriteData.DataClasses.TeacherData;
    
    import java.util.ArrayList;
    
    //https://dzone.com/articles/java-singletons-using-enum
    public enum SavedData {
        INSTANCE;
    
        private ArrayList<StudentData> studentData = new ArrayList<StudentData>();
        private ArrayList<TeacherData> teacherData = new ArrayList<TeacherData>();
        private ArrayList<LessonData> lessonData = new ArrayList<LessonData>();
        private ArrayList<GroupData> groupData = new ArrayList<GroupData>();
    
        // Getters and Setters
        public ArrayList<StudentData> getStudentData() {
            return studentData;
        }
        public void setStudentData(ArrayList<StudentData> studentData) {
            this.studentData = studentData;
        }
    
        public ArrayList<TeacherData> getTeacherData() {
            return teacherData;
        }
        public void setTeacherData(ArrayList<TeacherData> teacherData) {
            this.teacherData = teacherData;
        }
    
        public ArrayList<LessonData> getLessonData() {
            return lessonData;
        }
        public void setLessonData(ArrayList<LessonData> lessonData) {
            this.lessonData = lessonData;
        }
    
        public ArrayList<GroupData> getGroupData() {
            return groupData;
        }
        public void setGroupData(ArrayList<GroupData> groupData) {
            this.groupData = groupData;
        }
    
    
        public ArrayList<LessonData> getTeacherLessons(TeacherData teacher){
            ArrayList<LessonData> lessonsTeacher = new ArrayList<>();
            if(!lessonData.isEmpty()){
                for(LessonData lesson : lessonData){
                    if(lesson.getTeacher().getName().equals(teacher.getName())){
                        lessonsTeacher.add(lesson);
                    }
                }
                return lessonsTeacher;
            }
            else {
                return null;
            }
        }
    
        public ArrayList<LessonData> getClassroomLessons(ClassRoom classRoom){
            ArrayList<LessonData> lessonsClassroom = new ArrayList<>();
            if(this.lessonData.isEmpty()){
                for(LessonData lesson : this.lessonData){
                    if(lesson.getClassRoom().getRoomName() == classRoom.getRoomName()){
                        lessonsClassroom.add(lesson);
                    }
                }
                return lessonsClassroom;
            }
            else {
                return null;
            }
        }
    
        public ArrayList<LessonData> getStudentGroupLessons(GroupData studentGroup){
            ArrayList<LessonData> lessonsStudentGroup = new ArrayList<>();
            if(!this.lessonData.isEmpty()){
                for(LessonData lesson : lessonData){
                    if(lesson.getStudentGroup().getName().equals(studentGroup.getName())){
                        lessonsStudentGroup.add(lesson);
                    }
                }
                return lessonsStudentGroup;
            }
            else {
                return null;
            }
        }
    
	`

Voor vraag 2:
Ik heb hiervoor gekozen omdat ik dacht dat het makkelijk zou zijn om voor alles een soort database te hebben waar je dingen kan neerzetten en kan gebruiken. Een centraal punt wat makkelijk te bereiken is en waar je dingen kan opslaan, dit vond ik perfect klinken voor een singleton. Door een singleton te gebruiken kan je er zeker van zijn dat je altijd de juiste instance hebt van een class en omdat ze vaak vanuit elk punt binnengehaald kunnen worden is het makkelijk te gebruiken in andere classes. Nu had ik een normale singleton kunnen gebruiken maar ik heb een Enum singleton gebruikt. Na wat onderzoek blijkt het zo te zijn dat het een goede singleton is dat wordt ondersteunt door java zelf. Er zal altijd maar een instance zijn van die enum singleton, no questions asked. Er is veel meer over te vertellen maar dat zou dit verslag te lang maken, maar om te laten zien dat ik dit niet uit mn duim zuig heb ik deze link: https://dzone.com/articles/java-singletons-using-enum . Dit artikel legt uit waarom java enum singletons goed zijn om te gebruiken.


    
    package MainPackage.ReadWriteData;
    


    import Data.Rooms.ClassRoom;
    import MainPackage.ReadWriteData.DataClasses.GroupData;
    import MainPackage.ReadWriteData.DataClasses.LessonData;
    import MainPackage.ReadWriteData.DataClasses.StudentData;
    import MainPackage.ReadWriteData.DataClasses.TeacherData;
    
    import java.util.ArrayList;
    
    //https://dzone.com/articles/java-singletons-using-enum
    public enum SavedData {
    INSTANCE;

    private ArrayList<StudentData> studentData = new ArrayList<StudentData>();
    private ArrayList<TeacherData> teacherData = new ArrayList<TeacherData>();
    private ArrayList<LessonData> lessonData = new ArrayList<LessonData>();
    private ArrayList<GroupData> groupData = new ArrayList<GroupData>();

    // Getters and Setters
    public ArrayList<StudentData> getStudentData() {
        return studentData;
    }
    public void setStudentData(ArrayList<StudentData> studentData) {
        this.studentData = studentData;
    }

    public ArrayList<TeacherData> getTeacherData() {
        return teacherData;
    }
    public void setTeacherData(ArrayList<TeacherData> teacherData) {
        this.teacherData = teacherData;
    }

    public ArrayList<LessonData> getLessonData() {
        return lessonData;
    }
    public void setLessonData(ArrayList<LessonData> lessonData) {
        this.lessonData = lessonData;
    }

    public ArrayList<GroupData> getGroupData() {
        return groupData;
    }
    public void setGroupData(ArrayList<GroupData> groupData) {
        this.groupData = groupData;
    }


    public ArrayList<LessonData> getTeacherLessons(TeacherData teacher){
        ArrayList<LessonData> lessonsTeacher = new ArrayList<>();
        if(!lessonData.isEmpty()){
            for(LessonData lesson : lessonData){
                if(lesson.getTeacher().getName().equals(teacher.getName())){
                    lessonsTeacher.add(lesson);
                }
            }
            return lessonsTeacher;
        }
        else {
            return null;
        }
    }

    public ArrayList<LessonData> getClassroomLessons(ClassRoom classRoom){
        ArrayList<LessonData> lessonsClassroom = new ArrayList<>();
        if(this.lessonData.isEmpty()){
            for(LessonData lesson : this.lessonData){
                if(lesson.getClassRoom().getRoomName() == classRoom.getRoomName()){
                    lessonsClassroom.add(lesson);
                }
            }
            return lessonsClassroom;
        }
        else {
            return null;
        }
    }

    public ArrayList<LessonData> getStudentGroupLessons(GroupData studentGroup){
        ArrayList<LessonData> lessonsStudentGroup = new ArrayList<>();
        if(!this.lessonData.isEmpty()){
            for(LessonData lesson : lessonData){
                if(lesson.getStudentGroup().getName().equals(studentGroup.getName())){
                    lessonsStudentGroup.add(lesson);
                }
            }
            return lessonsStudentGroup;
        }
        else {
            return null;
        }
    }

}




 
## Reflectie week 5
Deze week is er weinig gebeurt qua werk, maar zeer veel in de dynamiek van onze projectgroep. Zoals ik in vorige stukken heb verteld: hoewel niet iedereen het framework wilde gebruiken is er niks gezegd en is er ook geen goed alternatief gegeven. De start van deze week op maandag hadden we weer een tutor gesprek. Maurice onze tutor, had vorige week ons de opdracht gegeven om een definitieve keuze te maken of we verder wilde gaan met het framework. We hadden er niet echt veel over gepraat en ieder is stilletjes gaan werken, en dus waren we het nog steeds niet allemaal eens. 
Degene die het meest tegenover elkaar stonden waren ik en Timo. Timo weigerde naar het framework te kijken en ik weigerde te stoppen met het framework zonder dat hij er ook maar een blik naar had geworpen. Het feit dat niemand iets zij en het grootse gedeelte van de groep wel het framework had geaccepteerd had het eigenlijk al te laat gemaakt voor deze discussie, veel dingen waren al gemaakt met het framework er onder. Maar de groep was nog wel verdeelt, na een lang gesprek met onze tutor is er weer uitgekomen dat we iedereen aan een kant moeten brengen. Ik had hier weinig vertrouwen in maar we gingen het proberen. We hadden ook de opdracht gekregen dat als het niet zou lukken dat we samen met de tutor zouden gaan zitten om het dan alsnog optelossen die week.
We zijn de volgende dag in een lokaal gaan zitten en daar zijn we een lange discussie begonnen. De discussie in een notendop is dat ik graag wilde dat als hij mijn framework niet goed vond dat hij vertelde waarom en wat het alternatief zou zijn. Ik heb nooit een ander antwoord gekregen dan dat hij niet naar mn framework wilde kijken omdat het extra werk zou zijn, verder was zijn alternatief een lijst van updateables die je in de main afspeelde. Dit is op zich niet fout maar is in principe een minder uitgebreide versie van m’n framework. Mijn framework is in een notendop updateables met 3 loops in plaats van 1 en ze kunnen op actief en inactief gezet worden tijdens runtime, dit is een grootte versimpeling maar het is wel waar het op neer komt. Hierdoor was ik het dus niet eens met zijn mening en zijn we er niet alleen uit gekomen. We hebben onze tutor een bericht gestuurd dat het ons niet gelukt is en dat we dus hulp nodig hebben.
De dag erna zijn we met onze tutor gaan zitten. Naast de discussie voortzetten over waarom we wel of niet het framework willen gebruiken heeft Maurice ons geholpen om het duidelijker te maken wat onze persoonlijke goals voor het project waren en waarom. Door dieper op elkaars beredenering in te gaan was het makkelijker elkaar te begrijpen. We hebben allemaal onze verschillen gehouden maar als groep snapte we elkaar nu beter. Er is uitgekomen dat het framework niet een slecht idee is en soms zoiets van mij aan te nemen omdat ik jaren meer ervaring heb, verder is er ook op gewezen dat ik meer kans heb gehad om te leren programmeren door m’n mbo-opleiding en dat ik het maken van een simpel framework al geleerd heb. Hierdoor had ik geen rekening gehouden dat de mensen uit mijn groep dit nog moeten leren en daarom het misschien zelf van uit niks wilde opbouwen. Dit is nooit gezegd maar is wel een mogelijkheid en dit zal onthouden voor mijn volgende groep.

 
##Reflectie week 6
Deze week heb ik vooral Lars geholpen met pathfinding. Na een redelijke tijd nadenken en discussiëren over wat we gingen doen kwamen we er uiteindelijk uit. We moesten rekening houden met het feit dat er best veel units gebruik van moesten maken en dan het makkelijk te maken was. Mijn eerste voorstel was het A* algoritme. We hadden al een grid map wat veel helpt voor A* maar de rest van de groep was er nooit echt mee in aanraking gekomen. Hierdoor keken we verder naar een andere oplossing. Tijdens de OGP-lessen en het voorbeeld van Johan werd het breath first search algoritme gebruikt. Dit algoritme gaat vanuit een punt naar de neighbours van dat punt en doet hetzelfde bij de neighbours tot er niks meer over is om naartoe te gaan. Door dat het zich over heel het grid uitbreidt kun je de punt laten wijzen naar waar ze vandaan komen. Als dit gedaan is kan je een unit naar de punten laten kijken en eroverheen laten lopen. Voor een betere uitleg raad ik aan om op deze pagina te kijken: https://www.redblobgames.com/pathfinding/tower-defense/ . Omdat dit algoritme door de lessen wordt gebruikt en het maar een keer iets hoeft te berekenen is het ook zeer geschikt voor het project. Lars is niet de enige geweest die ik heb geholpen deze week, groep b2 en b5 heb ik ook geholpen met het maken van hun pathfinding. Ik heb uiteindelijk een versie voor mezelf gemaakt om als voorbeeld voor de andere te gebruiken, wat best veel hielp met de uitleg.

 
Vakinhoudelijke reflectie:
Wat is de situatie (context)?
Er moet pathfinding in ons programma en we weten nog niet zeker wat voor pathfinding we gaan maken. Als we kijken naar het project hoeft er geen pathfinding te zijn die de hele tijd veranderd maar het moet wel redelijk efficient zijn.

Welke keuzemogelijkheden heb je?
We hebben een paar keuzes, 
•	A* pathfinding, dit is een van de meest robuuste manieren waarom je pathfinding kan maken maar word niet besproken tijdens de lessen van avans en het kan best moeilijk zijn voor een beginner. Ook loop je een risico dat je programma snel te zwaar wordt met veel units 
•	Een grid waar elke tile een richting aan geeft per route en de routes worden gemaakt met het breath first search algoritme, dit is relatief makkelijk te maken maar is niet geschikt voor routes die zich constand aan de omgeving moeten aanpassen. Ook is het ook niet handig als je en reis koste wil geven om zo paden te maken. Dingen zoals over gras kunnen lopen maar dat niet doen omdat de stoep efficiënter is kan je niet makkelijk implementeren.

Welke keuze heb je gemaakt?
Keuze 2, het breath first search grid.

Waarom heb je deze keuze gemaakt?
Dit word behandeld in de lessen waardoor iedereen het begrijpt. We hebben ook geen routes nodig die zich constant aanpassen waardoor dit goed te gebruiken is. Het is ook makkelijker te maken wat weer tijd gaat schelen. Na al dit te overwegen leek dit de juiste oplossing voor dat moment.
 
Reflectie week 7
Deze week ben ik bezig geweest met het helpen van de andere mensen in de groep en met een start van collision. Door corona gaat comunicatie wat moeilijker maar mensen proberen hun werk nog af te maken. Ik ben gestart aan het maken van mn collision en probeer mijn markdown een beetje te doen, helaas is programeren leuker dan documenteren dus er kwam niet veel van. Ik wilde collision maken voor de muren en collision avoidance later. Ik was van plan om een het nog te optimizen maar dat bleek niet nodig te zijn. Ik overschoot al snel mijn doel met collision. We hadden alleen maar circle colliders nodig en achteraf gezien maakte ik avoidance van de muren niet collision based. Nu had ik een collision system gemaakt met squares, points en cirkels en een systeem voor tags wat allemaal niet gebruikt werd.

 
## Reflectie week 9
Week negen, bijna bij het einde. Helaas is door corona het moeilijk geweest om samen te werken. Ik heb een poging gedaan voor avoidance wat helaas moeilijker wordt dan geplanned. Het grid is absoluut niet geschikt voor avoidance. Verder heb ik ook deel van mijn collision weg gehaald omdat het niet gebruikt werd en ik geen gedoe over complexity wilde hebben zoals met het framework. De code heb ik nogsteeds maar in de aparte repository van het framework. Voor de avoidance gaat het moeilijk worden om het optijd af te maken.

Vakinhoudelijke reflectie:
Wat is de situatie (context)?
Het project heeft collision avoidance nodig maar het grid is er absoluut niet geschikt voor. Nu kan ik de switch maken naar A* maar ik weet niet of dat een goed idee is. Ik kan ook proberen om het grid aan te passen en ik weet ook niet of dat een goed idee is. Wat er ook gebeurd het lijkt er op dat ik veel tijd kwijt ga zijn.

Welke keuzemogelijkheden heb je?
We hebben een paar keuzes, 
•	Maak een A* pathfinding met avoidance wat weer verreweg het meest solid is maar ook het moeilijkste. Het zal ook het langste duren helaas.
•	Pas het grid aan op een manier dat het geschikt is voor avoidance


Welke keuze heb je gemaakt?
Keuze 2, pas het grid aan.

Waarom heb je deze keuze gemaakt?
Omdat het maken van een A* pathfinding te lang zal duren en de rest van de groep zal het niet begrijpen. Mischien wordt het dan ook te zwaar maar en mischien word het integraten in het project te moeilijk. Er was te veel risico om het te proberen terwijl ik niet eens weet of het grid veranderen binnen de tijd gaat lukken.


 
## Gebruik van json:
Het is moeilijk te raden welke programma’s en websites json gebruiken, het is en blijft maar een manier van data weg schrijven in de zee van vele manieren. Als je een tekst bestandje maakt met dezelfde syntax als json maar er geen json achter zet is het dan nog steeds json? Hoe je dingen weg schrijft moet je per project bepalen en daarom is het moeilijk te raden wie wel json gebruikt en wie niet. Maar ik ken een paar games die tiled gebruiken dus neem ik aan dat deze games json gebruiken om hun mappen in op te slaan.
Deze games gebruiken Tiled: 
https://store.steampowered.com/app/647960/Rusted_Warfare__RTS/
http://evolonline.org/
https://store.steampowered.com/app/332200/Axiom_Verge/


