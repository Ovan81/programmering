# **loggbok**
länk till UF-repositoriet:https://github.com/luckelc/interactive_uf

länk till mitt blackjack:https://github.com/Ovan81/blackjack

länk till hobbyspelet:https://github.com/wedonthaveaname/casting-couch 

## *vecka 21 -- Blackjack är färdigt under filen "ezblackjack*
Denna veckan gjorde jag färdigt mitt blackjack, då jag fixade det som ej fungerade från förra vecka, fixade lite problem med kortens värden t.ex. att ess inte bytte mellan 1 och 11, och sedan importerade time för att göra lite delay mellan alla prints. Denna veckans programmering bestod alltså mestadels av felsökning, men inget var särskilt jobbigt.
## *vecka 20*

Denna veckan fick jag gjort ganska mycket trots att jag bara kunde arbeta på en av lektionerna. Jag har gjort en funktion för att kolla om man bustar, men min lösning för att se om man vinner fungerar inte super. Dessutom har jag nästan gjort färdigt en "hit or stand" funktion, men och nästa gång ska jag fixa så att denna funktionen kan urskilja mellan datorhanden och spelarhanden, eftersom detta ej funkar just nu.
## *vecka 19*
Denna veckan har jag kommit en bra bit i blackjacket, i filen kallad "ezblackjack". Nu kan jag dra kort ur en kortlek som försvinner, lägga dem i händer, bestämma deras värde och färg med mera. Jag började också att experimentera med olika rundor, så ett värde bestämmer vem som får spela, men jag bestämmde att detta ej kommer behövas. 

Detta och mer gjorde jag på fredagen:
    
    def cardindex (card): 
        cardvalue=card
        if cardvalue <= 13:
            None
        elif cardvalue >= 13 and cardvalue < 26:
            cardvalue -= 13
        elif cardvalue >= 26 and cardvalue < 39:
            cardvalue -= 26
        else:
            cardvalue -= 39
    
        if cardvalue == 1:
            cardvalue ="ace"
        elif cardvalue == 11:
            cardvalue = "knight"
        elif cardvalue == 12:
            cardvalue = "queen"
        elif cardvalue == 13:
            cardvalue = "king"
        else:
            None
        return cardvalue
        
        
    
    def addcardtohand(deck, hand):
            tempcard = deck[0]
            deck.pop(0)
            hand.append(tempcard)
    
    
    while play(question) == True:
        deck.clear
        for i in range(1,53):
            deck.append(i)
        random.shuffle(deck)
            
    
    
        addcardtohand(deck, playerhand)
        cardtype=cardsuit(playerhand[-1])
        cardvalue=cardindex(playerhand[-1])
        print("you got", cardvalue, "of", cardtype + "!")
    
        addcardtohand(deck, computerhand)
        cardtype=cardsuit(computerhand[-1])
        cardvalue=cardindex(computerhand[-1])
        print("The dealer got", cardvalue, "of", cardtype + "!")
    
        addcardtohand(deck, playerhand)
        cardtype=cardsuit(playerhand[-1])
        cardvalue=cardindex(playerhand[-1])
        print("you got", cardvalue, "of", cardtype + "!")
        
    
       
    
        question = ("do you want to play again? (y/n)")
        

    
## *vecka 18*
har helt glömt att skriva för denna veckan, men antar att jag fortsatte med det icke objektorienterade.

## *Vecka 17*
denna veckan började jag att fortsätta med blackjacket, och lärde mig var constuctors var och varför self används i python till skillnad från andra språk, för att förstå objektorienterad programmering bättre. Jag förstod hur det fungerar, men jag förstår inte riktigt varför man ska definiera constructors t.ex. genom att skriva __init__ istället för att inte skriva något alls.

på torsdagen så förstod jag att objektorienterad programmering ej är i kursen, så jag tänker göra ett snabbt blackjack för att ha ett färdigt bedömningsprojekt, för att sedan lära mig mer om objektorienterat igen. Starten med detta "ezblackjack" har gått smidigt, och jag tror jag blir färdig denna eller nästa vecka (kan dock vara en gnutta tidsomtimistkt.)

## * Vecka 16*
denna veckan fortsatte jag att göra blackjacket, och lärde mig mer om objekt. Jag skapade t.ex. en master funktion i "game" klassen, samt lärde mig att alla objekt bör ligga i game klassen, för dens objekt sedan ska ligga utanför.

## *Vecka 15*
Denna veckan har jag fixat den nya viktbaserade kortvalningen för mitt omgjorda blackjack. Nu fungerar det som en riktig kortlet, där den blandas, sedan dras det översta kortet från kortleken, men jag har inte hunnit göra att man drar än. 

    class Card:
        suit = ""
        def cardtype(self,deck):
            if deck[0] <= 13:
                self.suit= "clubs"
            elif deck[0] > 13 and deck[0] <= 26:
                self.suit = "diamonds"
            elif deck[0] > 26 and deck[0] <= 39:
                self.suit = "hearts"
            else:
                self.suit = "spades"
            print(self.suit)
        
        def cardvalue(self, deck): 
            if deck[0] <= 13:
                None
            elif deck[0] >= 13 and deck[0] < 26:
                deck[0] -= 13
            elif deck[0] >= 26 and deck[0] < 39:
                deck[0] -= 26
            else:
                deck[0] -= 39
            print(deck[0])
            
Detta är det jag gjort i "card-klassen" denna veckan, och jag tycker att denna lösningen känns smart. 
        

## *25/03*
från och med nästa vecka tänker jag skriva veckobaserat istället för lektionsbaserat, eftersom jag kommer arbeta mer hemma. 

Förra veckan på hobbyspelet fick jag online multiplayer att helt och hållet fungera, då jag och t.ex. joel kunde joina varandra via steam och ha syncad movement. 

på lektionen idag fixade jag min gamla kod så den fungerade bättre, samt diskuterade med Lucas angående hobbyspelet. Det gick ganska trögt idag, men jag tänker jobba ikapp på påsklovet. Det svåraste idag var nog att få funktionerna att agera exakt så jag ville, men inget var speciellt krävande. 

## *21/03*
idag började jag om med min blackjack eftersom min struktur var så dålig, så det var lättare att starta om helt enkelt. 

    class Deck:
        deck=[]
        def resetdeck(self):
            self.deck.clear()
            for i in range (1,53):
                self.deck.append(i)

Jag gjorde om min viktbaserade kortlek till dessa kodrader, man kan ju säga att det krymptes lite granna. Nästa sak jag ska göra är att välja suite och dra kort, men det är väldigt enkelt.
## *14/03*
Fortsatte med blackjacket, märkt att jag behöver ändra på mina klasser och helt hur kortutdelningen fungerar då den slutar fungera ifall alla kort av samma sort (alla klöver, spader, etc.) tar slut innan spelet tar slut. Jag kan lätt fixa detta genom att göra det till en lista med värden som jag omdefinerar istället för att göra det så som jag gjort. Detta är vad jag tänker göra nästa lektion!

## *07/03*
idag är mitt mål att få i ordning klasserna och fixa kortutdelningen, alltså få problemen från förra lektionen lösta.

Jag fortsatte på båda delarna och gjorde framsteg!
## *04/03*
idag fortsatte jag att ställa upp classerna i mitt projekt samt fixa med kortutdelningen, men jag har problem med hur jag ska spara korten som är kvar. Jag planerar att lösa detta nästa lektion.

## *26/02*
idag gjorde jag också UF då vi behöver bli helt färdiga med allt innan onsdag, men jag tänker att jag tar ikapp dessa tre lektionerna på fritiden när mässan har varit.

## *22/02*
Samma idag med, men gjorde lite programmering också.

## *19/02*
idag jobbade jag med Uf då vi behövde fixa inför UF-mässan.

## *08/02*

Idag fortsatte jag med blackjacket och försökte få klasserna att fungera så jag vill. Jag lade in ett sätt att märka om man skriver antal spelare som en integer, men jag hann inte jättemycket mer än det då jag också pratade med ronnie om att låna hårdvara för en server.
## *22/1*
idag kunde jag inte jobba få jag glömt min laddare på hogia, vi hade distans och jag hittade ingen usb-c med tillräckligt hög watt för att min dator skulle starta. när jag försöker öppna min pythonfil på min hemmadator klagade python på att jag saknar en microsoft redistributable som jag redan har.
## *18/1*
Idag fortsatte jag med viktbaserade funktionen i blackjack, för att kunna få reda på vilket kort jag tog ut ur hela kortleken. Det fungerar, men nu ska jag också komma på hur man kan använda det på ett rimligt sätt. Det har gått bra idag :)

## *15/1*
idag jobbade jag med blackjacket, och bestämde med dig att vi skulle göra det objekt-orienterat när jag blev färdig. Jag tyckte att ebbes var för rörigt, så jag började helt om från grunden, då jag tror att det kommer ta lika lång tid ändå.
Allt idag gick bra, men det svåraste var defenitivt att bestämma hur jag kunde ha en viktbaserad kortlista där man kan skilja på färgerna.
## *18/12*
Idag började jag med UF-spelets meny, och har fått det att fungera. Jag förstod mig inte riktigt på hur timer objektet fungerade, vilket jag ska försöka ta itu med nästa lektion. Generellt har det gått väldigt bra denna lektionen dock :)

## *11/12*
Idag satt jag hela lektionen med att ominstallera allt viktigt på min dator då "någon" laddade ner och startade en fil på min dator som hette "suicide-linux". Den tog bort hela mitt os, så efter att joel ominstallerade ubuntu tidigare så satt jag och fixade med github, wine, codium, med mera.

## *7/12*
idag gjorde jag först test, sedan återinstallerade jag github och vscodium eftersom vi har nya datorer och sist började jag på blackjack med ebbe :) Inget var hjättesvårt men det var tidskrävande och jag lärde mig mer om random importeringen, t.ex. att man importerar slumpat objekt i en lista med random.choice.

## *30/11*
idag började jag med "gradkonvertering extra" eftersom jag kände att jag inte gjort ett rikard projekt på ett tag. Jag har definerat hela funktionen jag behöver samt fått alla värden inmatade men jag behöver lite mer tid för att sätta ihop allt. Lägger in filen när jag blir fördig med den :)
## *25/11*
Eftersom vi ska byta datorer idag så lägger jag upp båda ofärdiga godotprojekten här :)


## *24/11*
Standup: idag ska jag lära mig om funktioner och fortsätta lära mig topdown spel.

Idag lärde jag mig om funktioner och fortsatte lite smått med spelet. Jag kände att funktioner inte var något speciellt svårt så det var najs. Jag märkte dock att videon jag följde förut inte var baserad i rätt version av godot, så jag byter till en annan video och börjar om. Det borde gå snabbare då jag redan kan mycket nu.
nya videon:https://www.youtube.com/watch?v=Luf2Kr5s3BM&t=2413s

## *23/11*
Idag gjorde jag inte mycket utom prover på lektionen för jag var väldigt trött. Jag jobbade dock programmering på studiepasser där jag fortsatte med grunderna för topdown spel, samt jag tänker jobba lite programamering på 5h bussresan imorgon.

## *20/11*
idag började jag egna tiden av lektionen med att plugga på listor och funktioner, för att sedan börja kolla på hur man gör ett top-down spel, eftersom borealis vill ha ett från vårt UF-företag. Nu börjar jag verkligen förstå mig på pixel formatet, tilemaps, tilesets och vad nodes, scenes och scripts är och hur de fungerar i godot. Det är lite ovant att se kod i gd eftersom det liknar javascript mer än python, men jag har använt javascript förut då jag har moddat spel jag spelat, alltså borde det inte vara världens största problem att lära mig det.


## *16/11*
Idag gjorde jag 2 prov, försökte fixa collissions i mitt spel och vi började brainstorma om spelet vi ska göra som UF-företag. Vi bestämde oss att vi behöver en touch-skärm av borealis innan vi borde börja med det spelet, så för tillfället fortsätter jag med mitt egna. Jag fick som sagt inte colissionsen att fungera idag men jag fortsätter med det nästa gång.

##*13/11*
idag började jag att göra ett spel enligt en tutorial, och det har gått väldigt bra. Jag har börjat lära mig om colission boxes, tilemaps, tilesets och hur man använder sig av sprites.
https://www.youtube.com/watch?v=5V9f3MT86M8&t=730s

## *6/11*
Idag satt jag både och uppdaterade datorn då archlinux strulade men också kollade jag på videor om hur man gör både top-down och 2d spel. Jag vet inte vilken jag vill göra än, då top-down kanske är jobbigare att göra men ger mer kreativ frihet i level-design.
videosarna jag kollade på: 
https://www.youtube.com/watch?v=-4jEXTwTsVI
https://www.youtube.com/watch?v=HycyFNQfqI0
https://www.youtube.com/watch?v=xFEKIWpd0sU
https://www.youtube.com/watch?v=9u6edV5-EEI

Just nu lutar jag mot en 2d-platformer.

## *23/10*
Vi satt nästan hela lektionen och försökte bestämma vad för sorts spel vi ska göra, och just nu tänker vi nog ett rogue-like platformer esque spel, lite likt hollow knight fast pixel art.

## *16/10*
Glömde av loggboken tills nu, men idag så läste jag på din hemsida om for-loopar, listor, lite funktioner samt kollade på följande länken om vilket språk man bör använda i godot.
https://www.youtube.com/watch?v=FmDgLyyEEYs

## *9/10*
fick äntligen github att fungera efter typ 10 försök! alla mina tidigare programmeringsuppgifter t.ex. sten sax påse försvann när jag bytte till linux efterom jag glömde att spara dem, men jag tänker börja lära mig godot nu och göra mitt egna projekt



