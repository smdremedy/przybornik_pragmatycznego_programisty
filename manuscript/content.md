
# Wstęp

{height:20%}
![](resources/images/smd.jpeg)

Cześć, nazywam się **Sylwester Madej** i od 7 lat pomagam ludziom tworzyć aplikacje na Androida. Poza kodowaniem, prowadzę także szkolenia stacjonarne i online w ramach **SzkoleniaAndroid.pl**. Często uczestnicy pytają się mnie o sprawdzone narzędzia, które warto poznać. Postanowiłem zebrać moje rekomendacje w tego ebooka.

Celem niniejszego ebooka jest przedstawienie zestawu narzędzi i zasobów, których używanie wpływa na jakość i wydajność pracy programisty. Każde z nich przetestowałem na własnej skórze, podczas tworzenia wielu aplikacji. Wybór ten potwierdziło wielu programistów, z którymi rozmawiałem na imprezach branżowych, takich jak Mobile Warsaw, Droidcon czy Mobilization.

Postarałem się wybrać po jednym elemencie, z każdej kategorii. W przypadku gdy znam inne, podobne rozwiązania, podaje je jako alternatywy. Ułatwia to proces wyboru osobom początkującym, choć sam wychodzę z założenia, że nie ma narzędzi idealnych do wszystkiego. Dlatego też sam co jakiś czas szukam nowych, lepszych rozwiązań.

Duża część wskazanych przeze mnie narzędzi jest bezpłatna. W przypadku rozwiązań płatnych podaję minimalną cenę, jaką musisz zapłacić jako niezależny programista, za najprostszą, ale funkcjonalną wersję produktu.

Mam nadzieję, że programiści zaczynający swoją przygodę z profesjonalnym tworzeniem aplikacji znajdą tu masę wskazówek, które pomogą im od samego początku pracować "zgodnie ze sztuką". W przypadku osób bardziej doświadczonych, liczę na to, że znajdziecie tutaj co najmniej 2-3 interesujące narzędzia, które przydadzą się w Wam w pracy.

Lubię książki, które podają konkretne kroki i od samego początku przynoszą wartość. Dlatego też mam prośbę: wybierz 1 narzędzie i zacznij z niego korzystać. Gwarantuję, że już po tygodniu zauważysz zmianę na plus!

# Narzędzia
Zacznę od crème de la crème spośród narzędzi do tworzenia aplikacji mobilnych, czyli produktów dostępnych jako aplikacje desktopowe lub wtyczki do takich aplikacji. Są to elementy, z którymi programista spędza najwięcej czasu. Starałem się, aby wybrane narzędzia dobrze się uzupełniały i stanowiły ekosystem, w którym praca staje się prostsza.

## Kotlin

{height:10%}
![](resources/images/kotlin.png)


| *Strona*      | https://kotlinlang.org/ |
| *Cena*        | FREE                                        |
| *Alternatywy* | Java            |



Zapomnij o Javie. Obecnie w świecie Androida liczy się tylko jeden język. Kotlin powstał jako wewnętrzny projekt twórców Android Studio, firmy JetBrains. Jednak łatwość integracji z AS i współpracy z Javą w projektach Androidowych spowodował, że coraz większa część programistów Androida postanowiła przenieść swoje projekty do Kotlina. 
Google zauważył ten trend i na Google I/O w 2017 ogłosił oficjalne wsparcie dla Kotlina, a w 2019 ogłosił Kotlina jako podstawowy język dla tej platformy.

Kotlin ma wiele zalet, ale przede wszystkim jest zwięzły:

```kotlin
data class Person(var name: String)
```

{pagebreak}

Odpowiednik w Java:

```java
public final class Person {
   @NotNull private String name;

   @NotNull
   public final String getName() {
      return this.name;
   }
   public final void setName(@NotNull String var1) {
      Intrinsics.checkParameterIsNotNull(var1, "<set-?>");
      this.name = var1;
   }
   public Person(@NotNull String name) {
      Intrinsics.checkParameterIsNotNull(name, "name");
      super();
      this.name = name;
   }
   @NotNull
   public String toString() {
      return "Person(name=" + this.name + ")";
   }
   public int hashCode() {
      return this.name != null ? this.name.hashCode() : 0;
   }
   public boolean equals(@Nullable Object var1) {
      if (this != var1) {
         if (var1 instanceof Person) {
            Person var2 = (Person)var1;
            if (Intrinsics.areEqual(this.name, var2.name)) { return true; }
         }
         return false;
      } else { return true; }
   }
}
```

Jeśli chcesz dowiedzieć się więcej, to sprawdź mój [darmowy mini-kurs Kotlina](https://szkoleniaandroid.pl/kurs-kotlina)

{pagebreak}

## Android Studio

{height:10%}
![](resources/images/as_logo.png)


| *Strona*      | https://developer.android.com/studio |
| *Cena*        | FREE                                        |
| *Alternatywy* | IntelliJ IDEA (€207)            |


Android Studio (AS) powstało jako rozwinięcie wsparcia dla Androida, dostępnego w edytorze IntelliJ IDEA Community Edition. 
Na Google IO 2013 zostało ogłoszone przez Google jako nowe oficjalne środowisko programistyczne (Integrated Development Environment, IDE) do tworzenia aplikacji na platformę Android. Dzięki połączeniu doskonałego IDE (latami dopracowywanego przez firmę JetBrains) z oficjalnym wsparciem zespołu Google, jest ono zdecydowanie lepsze od ADT (IDE opartego o Eclipse).

W celu maksymalizacji wydajności korzystania z AS, warto poświęcić trochę czasu i nauczyć się skrótów klawiszowych oraz poznać np. mechanizm szablonów generujący kod, który często się powtarza. Każda minuta poświęcona na naukę sztuczek w AS, to inwestycja w przyszłość. Istnieje wiele czynności, które da się przyśpieszyć np.: generowanie par getter/setter, refaktoryzacja kodu, czy chociażby obsługa systemów kontroli wersji z poziomu IDE.

{height:35%}
![Android Studio w trybie edycji layoutów z podglądem.](resources/images/as.png)

{pagebreak}

## Gradle (New Build System)

{height:10%}
![](resources/images/gradle_logo.png)


| *Strona*      | http://tools.android.com/tech-docs/new-build-system/ |
| *Cena*        | FREE                                                 |
| *Alternatywy* | Maven, Buck                                           |


Gradle został wybrany przez Google jako podstawa New Build System, który używany jest m.in. w Android Studio. Dzięki mechanizmowi zarządzania zależnościami wykorzystującymi istniejące repozytoria, używane dotychczas przez Maven, możliwe jest korzystanie z setek bibliotek. Wystarczy dodać do pliku build.gradle, po jednej linii tekstu, opisującej każdą z wymaganych zależności. Zastosowanie Gradle pozwoliło ujednolicić konfigurację projektu, dzięki czemu w chwili obecnej budowanie z linii poleceń oraz IDE wygląda tak samo i korzysta z tej samej konfiguracji.

Warto poświęcić kilka godzin, aby poznać bardziej zaawansowane możliwości systemu np. Flavors (smaki projektu), możliwość pisania fragmentów skryptu w języku Groovy lub Kotlin czy choćby opcje dostępne w Android Plugin dla Gradle.

{title="Prosty plik build.gradle dla aplikacji Android"}
```groovy
apply plugin: 'com.android.application'
android {
    compileSdkVersion 28
    defaultConfig {//podstawowa konfiguracja aplikacji
        applicationId "pl.szkoleniaandroid.myapplication"
        minSdkVersion 21
        targetSdkVersion 28
        versionCode 1
        versionName "1.0"
    }
    buildTypes {
        release {
            minifyEnabled true//włącz obfuskację przy budowaniu release
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'
        }
    }
}
dependencies {//zależności, czyli zewnętrzne biblioteki
    implementation 'androidx.appcompat:appcompat:1.0.2'
}
```

{pagebreak}

## Git

{height:10%}
![](resources/images/git_logo.png)


| *Strona*      | http://git-scm.com/    |
| *Cena*        | FREE                   |
| *Alternatywy* | Mercurial, SVN, Baazar |


Git to rozproszony system kontroli wersji, który powstał aby zarządzać kodem jądra systemu Linux. Jest podstawowym narzędziem, które każdy programista powinien sobie przyswoić, ponieważ pozwala współdzielić kod w zespole, podmieniać wersje, zapisuje również każda modyfikację pliku.

Git w chwili obecnej jest de facto standardem w projektach informatycznych i każdego dnia rośnie ilość narzędzi i usług, które powstały z myślą o nim. W przypadku starszych projektów, nadal można spotkać się jeszcze z narzędziem SVN, które jest rozwiązaniem słabszym, ze względu na konieczność korzystania z centralnego serwera.

Idea pracy z Git opiera się na zapisywaniu kolejnych wersji interesujących nas plików, w lokalnym repozytorium, które znajduje się w katalogu projektu. Dzięki temu możemy śledzić zmiany bez połączenia z siecią i synchronizować się z innymi członkami zespołu, tylko kiedy tego potrzebujemy.

![Przenoszenie zmian pomiędzy lokalizacjami lokalnymi i zdalnymi. Źródło: http://pl.wikibooks.org/wiki/Git/Podstawy](resources/images/git_flow.png)

Dużą wartością Git jest bardzo łatwy i lekki sposób pracy z gałęziami (branches), które pozwalają np. pisać nowe elementy aplikacji, jednocześnie mając dostęp do wersji stabilnej.

{pagebreak}

## Jenkins CI


{height:10%}
![](resources/images/jenkins_logo.png)


| *Strona*      | http://jenkins-ci.org/      |
| *Cena*        | FREE                        |
| *Alternatywy* | Travis CI, Bamboo, TeamCity |


Continous Integration (CI), to technika, w której serwer co pewien czas pobiera kod źródłowy i sprawdza czy uda się go skompilować, uruchomić i przetestować. Dzięki temu już w kilka minut po umieszczeniu zmian w systemie kontroli wersji, możemy się dowiedzieć czy coś zepsuliśmy np. poprzez mail rozsyłany do osób zainteresowanych.

Jenkins, to jedna z lepszych implementacji CI, a do tego darmowa. Dużą dodatkową zaletą jest możliwość skorzystania z dziesiątek pluginów, które potrafią obsługiwać różne narzędzia, systemy kontroli wersji lub po prostu wyświetlać czytelne raporty. Pluginem, który na pewno warto używać dla testowania aplikacji jest Android Emulator Plugin, który odpowiada za tworzenie emulatorów, uruchamianie ich i zarządzanie aktualnie uruchomionymi.


{height:20%}
![Prognoza jest dobra - buildy się udały. Źródło: https://www.morlunk.com/jenkins/](resources/images/jenkins_android.png)


Przykładowy cykl, który może realizować Jenkins CI:

1. Pobranie kodu z Git, SVN, Mercurial.

2. Zbudowanie paczki z użyciem Gradle.

3. Instalacja paczki na odpalonym na początku emulatorze, który działa na serwerze) lub urządzeniu.

4. Uruchomienie testów z wykorzystaniem np. Calabash lub Espresso.

5. Po udanym zbudowaniu i przetestowaniu, wysłanie do kanału Alpha w Google Play lub na jakąś usługę do dystrybucji paczek np. Crashlytics Beta.


{pagebreak}

## Sketch


{height:10%}
![](resources/images/sketch_logo.png)


| *Strona*      | https://www.sketch.com       |
| *Cena*        | $99/rok                                      |
| *Alternatywy* | Figma, Photoshop CC |


Sketch staje się w środowisku designerów następcą Photoshopa. Jego główne zalety to: dostosowanie do pracy z koncepcją ekranów, niska cena, prostota obsługi. Natomiast podstawowa wada, to konieczność korzystania z OS X.

Warto posiadać Sketch jeśli często otrzymujemy projekty graficzne wykonane w tym narzędziu i nie chcemy polegać na kimś, kto może akurat nie mieć czasu. Korzystanie z programu jest proste - można nawet używać go jako narzędzia do tworzenia Mockup'ów aplikacji.

Jest to produkt otwarty na rozwój, z dobrym community, co przekłada się na dużą ilość wtyczek, pozwalających m.in.: na szybki eksport grafik do różnych rozdzielczości. Widziałem nawet wersje, umożliwiające generowanie kodu layoutów prosto z projektu w Sketch.

{height:35%}
![Główne okno Sketch. Źródło: https://sketch.com](resources/images/sketch.png)

{pagebreak}

## InVision 

{height:10%}
![](resources/images/invision_logo.jpg)


| *Strona*      | https://www.invisionapp.com/ |
| *Cena*        | FREE (1 projekt)                      |
| *Alternatywy* | Zeplin, Avocode              |



Ważnym elementem każdego projektu jest współpraca na linii programista-designer. Jeszcze kilka lat temu oznaczało to, że programista musiał mieć dostęp do Photoshopa, albo musiał polegać na projektancie, który wyeksportuje mu widoki ekranów i zasoby graficzne do popularnego formatu graficznego (PNG, JPG).

Takie podejście powodowało stratę czasu i niedokładność w odwzorowaniu projektu wynikające np. z trudności zmierzenia odstępów pomiędzy elementami. Na szczęście pojawiła się cała gama rozwiązań, które ułatwiają tę współpracę. Ostatnio najczęściej korzystam z InVision. Jest to aplikacja webowa oraz zestaw pluginów do najpopularniejszych narzędzi graficznych.
W pierwszym kroku designer eksportuje projekt do InVision korzystają z pluginu, a następnie programista może sprawdzać odstępy, kolory i fonty użyte w projekcie oraz samemu eksportować zasoby graficzne do formatów rastrowych lub wektorowych.

{height:35%}
![Tryb inspect pozwala łatwo sprawdzić rozmiary i odstępy na projekcie. Źródło: https://www.invisionapp.com/](resources/images/invision_inspect.png)

{pagebreak}



## Postman – Rest client

{height:10%}
![](resources/images/postman_logo_only.png)


| *Strona*      | http://www.getpostman.com/ |
| *Cena*        | FREE                       |
| *Alternatywy* | RESTClient dla Firefox     |


Bardzo przydatny narzędzie, pozwalające na testowanie API REST, bez konieczności pisania kodu. Przyjemny interfejs użytkownika pozwala na zarządzanie wieloma zapytaniami jednocześnie i testowanie API, z którym będzie się komunikowała nasza aplikacja.

Do głównych zalet Postman'a należy zaliczyć:

* łatwość tworzenia wszelkiego rodzaju zapytań HTTP,

* obsługa metod uwierzytelnienia używanych w HTTP, w tym OAuth,

* formatowanie wyniku zapytania jako JSON lub XML,

* historia zapytań.

Narzędzie to warto wykorzystać, aby sprawdzić API zanim jeszcze zaczniemy implementować dane zapytanie po stronie aplikacji. Ponadto jest to idealne rozwiązanie dla programistów tworzących API, którzy chcą przetestować jak będzie się ono zachowywało dla prawdziwych danych.

{height:30%}
![Przykładowe zapytanie do API w Postman. Źródło: http://www.getpostman.com/](resources/images/postman-default-view.png)

{pagebreak}

## DB Browser for SQLite (dawniej SQLite Browser)

| *Strona*      | http://sqlitebrowser.org/           |
| *Cena*        | FREE                                |
| *Alternatywy* | SQLite Manager - plugin dla Firefox |

Kolejne proste narzędzie, które pomoże zaoszczędzić godziny przy tworzeniu aplikacji mobilnych. DB Browser, jak sama nazwa wskazuje, służy do przeglądania zawartości bazy SQLite. Poza przeglądaniem daje także możliwości edycji oraz wykonywania zapytań SQL i podglądu wyników. Jest to doskonała alternatywa dla konsolowego klienta *sqlite3*, który jest dostarczany z SDK Androida. Jedyną wadą jest konieczność pobrania pliku z urządzenia do lokalnego systemu plików np. poleceniem `adb pull`. Gdy to już zrobimy mamy gotowy plik, na którym możemy wykonywać dowolne operacje. Jeśli dokonamy jakichkolwiek zmian, to ten zmieniony plik musimy ponownie umieścić na urządzeniu za pomocą polecenia: `adb push`.

{height:40%}
![DB Browser pozwala m.in. podejrzeć strukturę bazy danych.](resources/images/dbbrowser.png)

{pagebreak}


## ScrCpy

| *Strona*      | https://github.com/Genymobile/scrcpy |
| *Cena*        | FREE |
| *Alternatywy* | Vysor, Mobizen                    |


Sposób na podejrzenie ekranu telefonu na ekranie komputera. Przydatne zwłaszcza gdy robimy demo dla klienta lub zespołu i potrzebujemy fizycznego urządzenia.


![Źródło: https://github.com/Genymobile/scrcpy](resources/images/scrcpy.jpg)


{pagebreak}

## Lottie

{height:10%}
![](resources/images/lottie_logo.png)


| *Strona*      | https://airbnb.io/lottie/ |
| *Cena*        | FREE                      |
| *Alternatywy* | -                         |



Biblioteka na Androida (i inne platformy) oraz plugin do After Effects. Pozwala na wyświetlanie w aplikacji bardzo efektownych wizualnie animacji, szczególnie przydatny przy tworzeniu splash screen, ekranów logowania i aplikacji lifestylowych, które muszą ładnie wyglądać.

Designer może projektować animacje korzystając z After Effects (de facto standard dla animacji), a następnie wyeksportować animację do pliku JSON i na tym jego rola się kończy.

Programista dodaje do projektu bibliotekę Lottie, wrzuca plik json do zasobów i w kilku liniach kodu jest w stanie zaimplementować dokładnie taki efekt jaki wymyślił designer. Żyjemy w przyszłości! ;)

![Ciężko zaprezentować animacje w ebooku. Wierzcie mi: są efektowne. Źródło: https://airbnb.io/lottie/](resources/images/lottie.png)

{pagebreak}


## JsonToKotlinClass

{height:10%}
![](resources/images/json_logo.png)


| *Strona*      | https://github.com/wuseal/JsonToKotlinClass |
| *Cena*        | FREE                          |
| *Alternatywy* | -                    |


Świetny plugin do AS i InteliJ Idea, pozwalający przekształcić kod JSON na obiekty modelowe w Kotlinie. Koniec z pracochłonnym, ręcznym budowaniem modelu na podstawie dokumentacji. Wystarczy wynik zapytania np. z Postmana i w kilku kliknięciach otrzymasz gotową strukturę klas.

{height:50%}
![](resources/images/json_to_kotlin.png)


# Usługi i narzędzia Web

## Shape Shifter

| *Strona*      | https://github.com/alexjlockwood/ShapeShifter |
| *Cena*        | FREE                                             |
| *Alternatywy* | -                                                |

Narzędzie online, które pozwala na pracę z animacjami na obrazach wektorowych. Interfejs użytkownika wygląda jak bardzo uproszczony Adobe Flash, ale pozwala tworzyć m.in. pliki zawierające AnimatedVectorDrawable.

Jest to bardzo dobry sposób na dodanie do aplikacji efektu WOW, bez konieczności tworzenia animacji w kodzie albo w ręcznie w plikach XML. Projekt jest ciągle rozwijany i zmierza w kierunku pełnoprawnego edytora.

{height:30%}
![](resources/images/shapeshifter.png)

{pagebreak}

## Android Pixel Calculator

| *Strona*      | http://angrytools.com/android/pixelcalc/ |
| *Cena*        | FREE                                     |
| *Alternatywy* | -                                        |

Wymiary obiektów na ekranie Androida można podawać w wielu jednostkach. Pixel Calculator pozwala sprawnie poruszać się pomiędzy tymi jednostkami. Dzięki temu można szybko przeliczyć wielkość w dp lub sp, niezależnie od tego dla jakiej gęstości został przygotowany projekt graficzny.

![W trybie prostym wystarczy podać wartość w jednej jednostce i gęstość, aby otrzymać pozostałe.](resources/images/pixel_calculator.png)

{pagebreak}

## Material Palette

| *Strona*      | http://www.materialpalette.com/ |
| *Cena*        | FREE                            |
| *Alternatywy* | -                               |

Szybki generator palety kolorów, do wykorzystania w aplikacjach zgodnych z Material Design. 

Wygenerowana paleta posiada kolory grawantujące dobry kontrast i czytelność. Jest to dobre rozwiązanie kiedy nie posiadam grafika w projekcie, a chcę aby aplikacja dobrze wyglądała. 

![Wystarczy dwa kolory główne i paleta gotowa](resources/images/material_palette.png)

{pagebreak}

## Github

{height:10%}
![](resources/images/github_logo.png)



| *Strona*      | https://github.com/ |
| *Cena*        | FREE                   |
| *Alternatywy* | Bitbucket, Gitlab         |


Github to od lat standard jeśli chodzi o przechowywanie kodu w publicznych repozytoriach. Tutaj lądują projekty Open Source, z których korzystasz. Tutaj rekruterzy szukają programistów, którzy nie wstydzą się swojego kodu. Po akwizycji przez Microsoft, Github pozwala też na przechowywanie nieograniczonej ilości prywatnych repozytoriów za darmo. Usługa ta sprawdza się to bardzo dobrze nawet dla dużych zespołów/projektów i pozwala zacząć pracę z Gitem, bez konieczności konfigurowania własnego serwera.

Ponadto serwis stał się swoistą siecią społecznościową dla programistów, a konto na Github stało się nowoczesną alternatywą dla CV. Często na rozmowach rekrutacyjnych konta Github uważane są za bardziej wartościowe niż suche wpisy o projektach w CV, ponieważ pozwalają zobaczyć jakość tworzonego kodu oraz sposób pracy nad projektem.

Dlatego też polecam założenie konta na Github każdemu programiście i tworzenie własnych projektów publicznych lub też udział w istniejących już przedsięwzięciach, poprzez zgłaszanie poprawek w postaci tzw. Pull Request.

{height:30%}
![Na Github można znaleźć kod wielu popularnych bibliotek OpenSource.](resources/images/github.png)

{pagebreak}

## Parse

{height:10%}
![](resources/images/logo_parseserver.png)


| *Strona*      | https://parse.com                                 |
| *Cena*        | FREE do 30 req/s                                  |
| *Alternatywy* | Firebase, Google AppEngine, Azure Mobile Services |


Parse było rozwiązaniem typu Mobile Backend as a Service, czyli część serwerowa dla naszej aplikacji, bez konieczności pisania kodu. Twórcy tej usługi postawili sobie za cel uproszczenie do maksimum czynności, które do tej pory trzeba było implementować w API.

Niestety, Facebook najpierw kupił Parse.com, a potem postanowił zawiesić jej działanie (czyli typowy przykład acqui-hire). Na szczęście jednak duża część kodu została udostępniona jako Parse Server, który każdy może zainstalować na własnym serwerze. Jeśli nie chcemy zajmować się instalacją rozwiązania, to możemy skorzystać z jednego z dostawców, którzy oferują hosting pod jednym kliknięciem np. https://back4app.com. Sam często wykorzystuje to rozwiązanie na szkoleniach, dzięki czemu uczestnicy mogą sami stworzyć własną instancję serwera w kilka minut, bez konieczności płacenia w ramach limitów deweloperskich (np. max 10 req/sec).


![Widok danych pozwala zarządzać bazą w prosty sposób.](resources/images/parse.png)

Mamy więc mechanizm operowania na danych w tabelach, wysyłanie wiadomości PUSH, analitykę, logowanie FB i Twitter, a nawet pisanie logiki po stronie serwera w JS.

Przykładowo: utworzenie backendu dla aplikacji typu Tinder nie wymaga od nas pisania kodu, ponieważ możemy skorzystać z:

* logowania FB i automatycznego tworzenia kont w Parse,

* zapisywania profili, wiadomości, położenia użytkownika w odpowiednich tabelach,

* wyszukiwania użytkowników w określonej odległości dzięki geoquery,

* powiadamiania użytkownika o nowych aktywnościach na profilu, poprzez wiadomości PUSH.



{pagebreak}

## Firebase

https://firebase.google.com/

Firebase zaczynało jako alternatywa do Parse, mBaaS pozwalający na przechowywanie danych z możliwością odświeżania aplikacji w czasie rzeczywistym t.j. po każdej modyfikacji danych na serwerze. Google kupując Firebase przekształcił je w kombajn dostarczający wszystko co może przydać się twórcą aplikacji mobilnych. Obecnie Firebase zawiera m.in.:

* bazę danych (odpowiednik Parse),  
* bazę danych pracującą w trybie Real Time,
* obsługę autentykacji użytkowników (logowanie, rejestracja itp.),
* miejsce na plików użytkowników,
* możliwość pisania logiki w JS,
* zbieranie informacji o błędach w aplikacji (patrz Crashlytics),
* obsługę wysyłania wiadomości Push do użytkowników,
* i masę innych.

Model biznesowy przypomina trochę dealera narkotyków: dla bardzo małych aplikacji aplikacja 

{height:40%}
![Pod nazwą Firebase kryje się naprawdę dużo narzędzi.](resources/images/firebase_services.png)


{pagebreak}

## Firebase Crashlytics

{height:10%}
![](resources/images/crashlytics_logo.png)


| *Strona*      | https://firebase.google.com/docs/crashlytics/          |
| *Cena*        | FREE                               |
| *Alternatywy* | Applause, Splunk MINT |


Każda aplikacja umieszczona na sklepie wcześniej lub później będzie miała crashe. Nie da się tego uniknąć, bo nie da się też przetestować aplikacji na każdym z dziesiątek tysięcy urządzeń. Dlatego warto wyposażyć naszą aplikację w mechanizm automatycznego zgłaszania błędów, który w przypadku wystąpienia błędu wyśle krótką wiadomość na nasz serwer. Crashlytics sprawdza się w tej roli świetnie, a dodatkowo posiada piękny interfejs web, na którym można przeglądać informację o zaistniałych błędach łącznie z informacjami, na jakim modelu, wersji systemu i sprzęcie wystąpiły.

W przypadku, gdy korzystaliśmy z mechanizmu obfuskacji w ProGuard, będziemy potrzebowali pliku z mapowaniem, ponieważ nazwy metod w których wystąpił błąd będą już zmienione.

{pagebreak}

## Firebase Lab


| *Strona*      | https://firebase.google.com/products/test-lab |
| *Cena*        | FREE (5 testów/dzień)                  |
| *Alternatywy* | Appthwack, Saucelabs  |


Firebase Lab jest jedną z wielu, bardzo podobnych usług do testowania aplikacji mobilnych. W odpowiedzi na zwiększającą się fragmentację urządzeń korzystających z systemu Android, pojawiły się problemy z przetestowaniem aplikacji na dużej liczbie różnych urządzeń. Pojawił się więc pomysł, aby stworzyć miejsca, gdzie można uzyskać dostęp do dużej liczby fizycznych urządzeń, w zamian za niewielką opłatę. 

Tak jak wspomniałem, serwisów takich jest wiele. Różnią się liczbą dostępnych urządzeń, ceną oraz rodzajami testów jakie da się na nich uruchomić. Rzeczą, która wyróżnia Firebase Lab jest możliwość założenia darmowego konta i dostęp do kilku darmowych urządzeń. To pozwala na zapoznanie się z zasadami funkcjonowania serwisu oraz na przeprowadzanie testów na kilku dodatkowych urządzeniach.

Dodatkową cechą wyróżniającą, jest integracja z Android Studio oraz wieloma usługami CI.

![Wystarczy wrzucić plik APK i już można testować.](resources/images/firebase_lab.png)

{pagebreak}


## Apiary


{height:10%}
![](resources/images/apiary_logo.png)

| *Strona*      | https://apiary.io |
| *Cena*        | FREE                    |
| *Alternatywy* | -                       |

Większość aplikacji mobilnych na pewnym etapie swojego rozwoju zaczyna korzystać z API (zwykle REST), które często powstaje równolegle z aplikacją. Apiary ma za zadanie ułatwić proces współpracy pomiędzy twórcami API, a twórcami aplikacji.

Apiary stanowi interaktywnej dokumentacji API, która opisuje jakie endpointy są dostępne i jednocześnie pozwala wystawić tzw. mock czyli zaślepkę zwracającą wbite na sztywno dane.

Dzięki temu programiści mobilni mogą zacząć tworzyć i testować aplikację zanim powstanie infrastruktura serwerowa. Oczywiście zakładając, że dokumentacja będzie zgodna z rzeczywistością. 

{height:30%}
![Przykładowe API wystawione przez apiary. Źródło: https://apiary.io](resources/images/apiary.jpeg)

{pagebreak}


## StackOverflow

{height:10%}
![](resources/images/stackoverflow_logo.png)


| *Strona*      | https://stackoverflow.com/ |
| *Cena*        | FREE                    |
| *Alternatywy* | -                       |


StackOverflow jest najczęściej na pierwszym miejscu jeśli zadasz w Google pytanie, o konkretny problem. Baza licząca ponad pół miliona pytań dotyczących samego Androida, pozwala często uniknąć godzin siedzenia w poszukiwaniu rozwiązania problemu. Warto jednak wiedzieć, dlaczego to co wklejamy działa, tak aby nie zostawić w swoim kodzie magicznej *czarnej skrzynki*, której każdy boi się dotknąć.

StackOverflow to jednak dużo więcej niż zbiór pytań i odpowiedzi. To społeczność programistów, którzy chętnie dzielą się wiedzą. Wszystko wspomagane systemem punktowym, który pozwala wyróżnić się aktywnym użytkownikom. Dobra reputacja (punkty są nazywane właśnie reputacją) na StackOverflow, to obok konta Github, ważny element wyróżniający CV.

![Wśród 624 tysięcy pytań o Androida, może znajdziesz odpowiedź na swoje.](resources/images/stackoverflow.png)

{pagebreak}



## Proto.io

{height:10%}
![](resources/images/protoio_logo.png)


| *Strona*      | https://proto.io   |
| *Cena*        | FREE (max 5 ekranów)                      |
| *Alternatywy* | FluidUI, Balsamiq Mockups |


Klikalne prototypy stanowią jedną z najlepszych form dokumentacji w komunikacji programista<->klient. Pozwalają przedstawić potrzebne ekrany, sposoby nawigacji pomiędzy nimi oraz przetestować aplikację na żywym organizmie, bez konieczności uruchamiania IDE. Bardzo często zmniejszają ryzyko niedomówień lub ujawniają braki w projekcie.

Warto zacząć tworzenie prototypu już na etapie tworzenia lub czytania specyfikacji. Najlepiej jeśli jest to mockup typu Lo-Fi (niskiej szczegółowości, bez graficznych ozdób), tak aby klient nie przywiązywał się do jego wyglądu, tylko skupiał na nawigacji i kompletności danych.

Proto.io jest przykładem rozwiązania, które pozwala zaprojektować ekrany, dodać proste akcje (np. przejścia pomiędzy ekranami po naciśnięciu przycisku) i zaprezentować wynik w przeglądarce na telefonie klienta. Wystarczy przesłać link do wygenerowanego prototypu, który potencjalny użytkownik, może sobie przetestować na urządzeniu.

{height:35%}
![Proto.io pozwala łatwo tworzyć nawigację między ekranami. Źródło: https://proto.io](resources/images/proto.png)

{pagebreak}

# Biblioteki
Każdy programista dochodzi do takiego momentu, gdy stwierdza, że coraz więcej kodu, który pisze się powtarza. Dlatego właśnie tak ważne jest w projektach korzystanie z bibliotek, zwłaszcza z tych, które są sprawdzone i uznawane za standard. Dzięki temu, ktoś kto będzie przeglądał nasz projekt od razu będzie czuł się jak w domu.

## Android Jetpack

{height:10%}
![](resources/images/jetpack-hero.png)


| *Strona*      | https://developer.android.com/jetpack   |
| *Cena*        | FREE                                 |
| *Alternatywy* | - |



Jetpack to duży ukłon firmy Google w kierunku programistów. Jest to zestaw bibliotek i narzędzi, które stworzone zostały, aby dobrze się uzupełniać i tworzyć spójną architekturę. Warto przejrzeć je wszystkie, przynajmniej pobieżnie, a szczególną uwagę zwrócić na [Architecture Components](https://developer.android.com/topic/libraries/architecture/).

### Data Binding

Biblioteka pozwalająca na łączenie widoków z danymi na poziomie plików XML z Layoutami. W najprostszym przypadku pozwala pozbyć się findViewById(), jednak zwykle używana jest do odseparowania logiki od prezentacji z użyciem wzorca MVVM (Model-View-ViewModel).

### ViewModel
Bardzo prosta biblioteka zdejmująca z programisty błędogenny proces przechowywania stanu obiektów pomiędzy zmianami konfiguracji poprzez automatyczne zarządzanie cyklem życia obiektów typu ViewModel z MVVM.

### Room
Bardzo dobrze napisana biblioteka ORM (do mapowania obiektowo-relacyjnego), która upraszcza pracę z bazą SQLite w naszej aplikacji. Większość kodu generowana jest na etapie kompilacji na podstawie metadanych, które podamy m.in. zapytań SQL. Ważną zaletą jest dobra integracja z Android Studio, która pozwala m.in. na podpowiadanie kodu przy pisaniu zapytań SQL. 

### LiveData
Implementacja wzorca Obserwatora, która doskonale pozwala łączyć powyższe elementy, dzięki czemu np. widok (DataBinding) może reagować na zmiany w bazie danych (Room) poprzez obiekt LiveData przechowywany w ViewModelu.
Obiekty typu LiveData pozwalają na przekształcanie obiektów między warstwami naszej aplikacji lub łączeniem kilku obiektów w jeden. 

{pagebreak}


## Biblioteki Square


### Retrofit

| *Strona*      | https://square.github.io/retrofit/   |
| *Cena*        | FREE                                 |
| *Alternatywy* | Ktor, Volley |

Retrofit to najprzyjemniejszy sposób korzystania z API REST z poziomu Androida. Naszym zadaniem jest napisanie interfejsu zawierającego wszystkie metody, które będziemy chcieli wywołać na API, oraz dorzucenie anotacji, które opisują pod jakie URL-e mają te zapytania uderzać, jakie parametry wysyłać i co odbierać.

Resztę generuje za nas Retrofit. Otrzymujemy konkretną klasę, na której możemy wywoływać te metody. Wbudowana obsługa GSON, zapewnia nam automatyczne mapowanie obiektów POJO na JSON i odwrotnie. Łatwiej się nie da.


Przykładowy interfejs opisujący API:

```java
public interface GitHubService {
  @GET("users/{user}/repos")
  Call<List<Repo>> listRepos(@Path("user") String user);
}
```

Na jego podstawie Retrofit może szybko wygenerować implementację klienta HTTP:

```java
Retrofit retrofit = new Retrofit.Builder()
    .baseUrl("https://api.github.com/")
    .build();

GitHubService service = retrofit.create(GitHubService.class);
```

Teraz wystarczy tylko zawołać wygenerowaną metodę i pronto!

```java
Call<List<Repo>> repos = service.listRepos("octocat");
```

{pagebreak}

### Picasso

| *Strona*      | http://square.github.io/picasso/       |
| *Cena*        | FREE                                   |
| *Alternatywy* | Glide, Universal Image Loader |

Picasso to biblioteka służąca do wyświetlania obrazków z internetu. Kropka. Posiada proste API i automatyzuje pobieranie plików graficznych, zmianę ich rozmiaru, wyświetlanie w ImageView, cache w pamięci ram i flash. Dzięki temu możemy skupić się na tym, co ma być wyświetlone, a nie jak.


```java
Picasso.get()
    .load(url)
    .placeholder(R.drawable.user_placeholder)
    .error(R.drawable.user_placeholder_error)
    .into(imageView);
```

![Źródło: http://square.github.io/picasso/](resources/images/picasso_sample.png)

{pagebreak}


### Leak Canary

| *Strona*      | https://github.com/square/leakcanary |
| *Cena*        | FREE                            |
| *Alternatywy* | -              |


Wycieki pamięci to temat, z którym każdy programista Androida musi się zmierzyć. Często wynikają z nieznajomości architektury Androida lub cyklu życia jego komponentów, ale czasem są następstwem użycia jakiegoś mechanizmu cache lub źle napisanej biblioteki. Powodów może być wiele i często samo zdiagnozowanie takiego wycieku jest trudniejsze niż jego usunięcie.

I tutaj wchodzi Leak Canary, cały na biało. Jest to biblioteka wyszukująca wycieki pamięci, którą integruje się z aplikacją. Jeśli wyciek zostanie zlokalizowany to otrzymamy notyfikację, która po kliknięciu wyświetli nam szczegóły wycieku. Wszystko bezpośrednio na urządzeniu testowym lub emulatorze.

Polecam zwłaszcza początkującym programistom, którzy nie wiedzą jeszcze jakie konstrukcje prowadzą do wycieków (np. anonimowe klasy wewnętrzne), ponieważ da im to szybką informację o potencjalnych problemach.

![Uuups. Obiekt aplikacji trzyma referencje do widoków. Źródło: https://github.com/square/leakcanary](resources/images/leak_canary.png)


{pagebreak}

### Timber

{height:10%}
![](resources/images/timber.png)


| *Strona*      | https://github.com/JakeWharton/timber |
| *Cena*        | FREE                            |
| *Alternatywy* | -              |

Timber to narzędzie proste i przyjemne. Jest to nakładka na mechanizm logowania wbudowany w Androida. Pozwala szybciej dodać log do aplikacji (np. ograniczając konieczność podawania TAG) oraz zwiększa kontrolę nad logowaniem w całej aplikacji np. pozwalając na usunięcie logów jedną flagą.

{pagebreak}

## Dagger 2

| *Strona*      | https://github.com/google/dagger |
| *Cena*        | FREE                            |
| *Alternatywy* | Koin              |

Dagger to implementacja wzorca Dependency Injection, czyli wstrzykiwania zależności. Celem tego podejścia jest minimalizacja ilości miejsc, w których tworzymy obiekty poprzez `new NazwaKlasy()` i utworzenie centralnego repozytorium obiektów, które możemy wstrzyknąć w dowolnym miejscu aplikacji. 

W przypadku Androida jest to szczególnie przydatne, ponieważ często potrzebujemy w różnych Activity albo Fragmentach dostępu do np. SharedPreferences. Polecam przeczytanie dokumentacji i rozpoczęcie od wstrzykiwania prostych obiektów np. swoich Managerów.


```java
@Module
class DripCoffeeModule {
  @Provides static Heater provideHeater() {
    return new ElectricHeater();
  }

  @Provides static Pump providePump(Thermosiphon pump) {
    return pump;
  }
}

@Component(modules = DripCoffeeModule.class)
interface CoffeeShop {
  CoffeeMaker maker();
}

CoffeeShop coffeeShop = DaggerCoffeeShop.builder()
    .dripCoffeeModule(new DripCoffeeModule())
    .build();
```

{pagebreak}

## RxJava

{height:10%}
![](resources/images/Rx_logo.png)



| *Strona*      | https://github.com/ReactiveX/RxJava |
| *Cena*        | FREE                                   |
| *Alternatywy* | -                                      |

Biblioteka RxJava, pozwala wprowadzić do Javy nowy paradygmat - programowanie reaktywne (Reactive Programming). Jest to podejście upraszczające w znaczny sposób kod, którego zadaniem jest zarządzanie wieloma zadaniami asynchronicznymi, zwłaszcza takimi, które operują na danych. Dobrym przykładem jest fragment aplikacji wymagający np. jednoczesnego wywołania wielu zapytań HTTP i połączenia ich wyników. 

RxJava nie jest biblioteką, którą mogę polecić początkującym programistom. Jeśli jednak Twoje aplikacje stają się coraz większe i rośnie liczba zdarzeń lub zapytań HTTP, które wysyłasz to polecam przestudiowanie dokumentacji https://github.com/ReactiveX/RxJava/wiki.


```java
Flowable.range(1, 10)
  .parallel()
  .runOn(Schedulers.computation())
  .map(v -> v * v)
  .sequential()
  .blockingSubscribe(System.out::println);
```

{height:20%}
![Diagramy kulkowe (marble diagrams) pozwalają lepiej zrozumieć działanie operatorów Rx. Źródło: https://rxmables.com](resources/images/marble.png)

{pagebreak}

## Flipper

{height:10%}
![](resources/images/logo_flipper.png)



| *Strona*      | https://fbflipper.com/ |
| *Cena*        | FREE                       |
| *Alternatywy* | Stetho     |

Flipper to biblioteka od Facebooka, która pozwala debugować aplikację z użyciem dedykowanej aplikacji desktopowej. Pozwala, w czasie rzeczywistym, podglądać hierarchię widoków, zawartość bazy danych i SharedPreferences, a nawet monitorować zapytania HTTP.

{height:30%}
![Podgląd bazy danych na telefonie zdecydowanie ułatwia debugowanie. Źródło: https://fbflipper.com/](resources/images/flipper_db.png)


Integracja jest bardzo łatwa i sprowadza się do dodania zależności w Gradle oraz zainicjalizowania biblioteki przy starcie aplikacji.

```java
public class MyApplication extends Application {
  public void onCreate() {
    super.onCreate();
    SoLoader.init(this, false);
    if (BuildConfig.DEBUG && FlipperUtils.shouldEnableFlipper(this)) {
      final FlipperClient client = AndroidFlipperClient.getInstance(this);
      client.addPlugin(new InspectorFlipperPlugin(this, DescriptorMapping.withDefaults()));
      client.start();
    }
  }
}
```

Opcjonalnie można dodać jeszcze interceptor do OkHttp, aby móc podsłuchiwać ruch HTTP.

```java
new OkHttpClient.Builder()
    .addNetworkInterceptor(new FlipperOkhttpInterceptor(networkFlipperPlugin))
    .build();
```

{pagebreak}

## BindingCollectionAdapter

| *Strona*      | https://github.com/evant/binding-collection-adapter |
| *Cena*        | FREE                       |
| *Alternatywy* | -    |

Prosta biblioteka, która sprawi, że zapomnisz jakim bólem było pisanie adapterów do ListView i RecyclerView. Doskonale uzupełnia Data Binding i pozwala na automatyzację łączenia elementów kolekcji w ViewModelu z layoutami, eliminując tym samym masę boilerplate code.

Łatwo można dodać obsługę wielu typów elementów na liście albo np. dodać obsługę kliknięcia na elemencie.

Przykładowe użycie w ViewModelu:

```java
public class ViewModel {
    //place your models here
    public final ObservableList<String> items = new ObservableArrayList<>();
    //describe how they should bind to layouts
    public final ItemBinding<String> itemBinding = 
        ItemBinding.of(BR.item, R.layout.item);
}
```

I potrzebna konfiguracja w XML:
```xml
<!-- layout.xml -->
<layout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto">
    <data>
      <import type="com.example.R" />
      <variable name="viewModel" type="com.example.ViewModel"/>
    </data>

    <ListView
      android:layout_width="match_parent"
      android:layout_height="match_parent"
      app:items="@{viewModel.items}"
      app:itemBinding="@{viewModel.itemBinding}"/>

    <androidx.recyclerview.widget.RecyclerView
      android:layout_width="match_parent"
      android:layout_height="match_parent"
      app:layoutManager="androidx.recyclerview.widget.LinearLayoutManager"
      app:items="@{viewModel.items}"
      app:itemBinding="@{viewModel.itemBinding}"/>
</layout>

<!-- item.xml -->
<layout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto">
    <data>
      <variable name="item" type="String"/>
    </data>
    <TextView
      android:id="@+id/text"
      android:layout_width="match_parent"
      android:layout_height="wrap_content"
      android:text="@{item}"/>
</layout>
```

{pagebreak}


# Narzędzia związane z bezpieczeństwem

## Burp Suite

{height:10%}
![](resources/images/burp_logo.png)


| *Strona*      | https://portswigger.net/burp |
| *Cena*        | FREE                         |
| *Alternatywy* | CharlesProxy, Fiddler, Mitmproxy |



BurpSuite pozwala na debugowanie komunikacji HTTP pomiędzy aplikacją mobilną, a serwerem. Do działania wykorzystuje mechanizm proxy, czyli urządzenia, przez które przechodzi cały ruch sieciowy. Wystarczy wystartować program i ustawić na urządzeniu nasz komputer, jako serwer proxy, aby móc podejrzeć każdy bajt informacji przesyłany po HTTP, nawet w przypadku szyfrowania SSL.

Właśnie wsparcie dla SSL oraz prostota obsługi sprawiają, że narzędzie to może oszczędzić godziny. Często korzystam też z narzędzia interceptor, które niczym w debugerze, pozwala przerwać request w trakcie i np. zmodyfikować odpowiedź z serwera, jeśli chcę przetestować inny przypadek.

Dodatkowo, polecam czasem przeanalizować co wysyłają na serwer inne aplikacje lub np. usługi Google.

{height:40%}
![Podsłuchiwanie ruchu HTTPS wymaga jedynie zainstalowania root CA.](resources/images/burp_suite.png)


{pagebreak}

## JADX

| *Strona*      | https://github.com/skylot/jadx |
| *Cena*        | FREE                         |
| *Alternatywy* | Dex2Jar |

Dekompilator bajtkodu w formacie dex do Java. Pozwala zobaczyć zawartość wygenerowanego przez nas pliku APK i przeanalizować czy nie zostawiamy w kodzie zbyt dużo informacji, które ktoś może wykorzystać do niecnych celów.

Podstawowe narzędzie do statycznej analizy w przypadku testów bezpieczeczeństwa oraz debugowania kwestii związanych np. z obfuskacją kodu przez ProGuard albo R8.

![Zdekompilowany kod jest zaskakująco czytelny. Źródło: https://github.com/skylot/jadx](resources/images/jadx.png)

{pagebreak}

## Apktool

{height:10%}
![](resources/images/logo_apktool.png)


| *Strona*      | https://ibotpeaches.github.io/Apktool/ |
| *Cena*        | FREE                         |
| *Alternatywy* | - |

Najlepsze narzędzie do modyfikacji aplikacji na Androida. Pozwala rozpakować plik APK, zamienić bytecode na bardziej czytelny format SMALI. Pliki te mogą być modyfikowane, a następnie znów pakowane do pliku APK. 
Dzięki temu można modyfikować zachowanie aplikacji lub jej wygląd.


{pagebreak}


## Xposed Framework

{height:10%}
![](resources/images/xposed_logo.png)


| *Strona*      | https://github.com/rovo89/XposedBridge |
| *Cena*        | FREE                         |
| *Alternatywy* | Frida |

Framework pozwalający na method hooking czyli podmianę implementacji aplikacji na poziomie systemu. Dzięki temu, można modyfikować zachowanie aplikacji, bez konieczności modyfikacji plików APK.
Poza tworzeniem własnych modułów (kodu modyfikującego zachowanie), można także skorzystać z istniejących modułow, które modyfikują zachowanie popularnych aplikacji lub nawet systemu. Przykładem są moduły wyłączające SSL Pinning np. JustTrustMe. 

{pagebreak}


## Drozer

{height:10%}
![](resources/images/drozer_logo.png)


| *Strona*      | https://labs.f-secure.com/tools/drozer/ |
| *Cena*        | FREE                         |
| *Alternatywy* | - |

Drozer to narzędzie przyśpieszające analizę aplikacji bezpośrednio na urządzeniu. Pozwala badać jakie komponenty aplikacji są dostępne z punktu widzenia innych aplikacji. Posiada nawet skanery wyszukujące automatycznie podatności Path Traversal i SQLInjection.

Drozer składa się z agenta, którego instaluje się na urządzeniu i tekstowej konsoli, która się z nim łączy i pozwala nim sterować.

## Kali Linux

{height:10%}
![](resources/images/kali_logo.png)


| *Strona*      | https://www.kali.org/ |
| *Cena*        | FREE                         |
| *Alternatywy* | Santoku |

Dystrybucja Linuxa stanowiąca podstawowe narzędzie wszystkich ludzi zajmujących się zagadnieniami Security niezależnie od platformy i strony. Zawiera większość narzędzi do testowania sieci komputerowych, reverse engineeringu czy socjotechnik.

Doskonale sprawdza się jako baza do testowania aplikacji mobilnych, choć może wymagać doinstalowania kilku narzędzi z repozytorium.

{pagebreak}



# Kody źródłowe

## Plaid 

https://github.com/android/plaid

{height: 30%}
![Źródło: https://github.com/android/plaid](resources/images/plaid.png)

Przeglądarka wiadomości ze stron Designer News, Dribbble i Product Hunt stworzona przez ludzi z zespołu Androida. Bardzo dobrze ilustruje sposób implementacji Material Design oraz architektury w oparciu o Architecture Components.

{pagebreak}


## Google IO App

https://github.com/google/iosched


{height: 30%}
![Źródło: https://github.com/google/iosched](resources/images/iosched.png)


Każdego roku Google IO jest najważniejszą konferencją, na której ekipa z Mountain View prezentuje nowości w SDK Androida. Niedługo po tym wydarzeniu udostępniany jest kod źródłowy oficjalnej aplikacji, powstałej na to wydarzenie, która jednocześnie prezentuje jak najwięcej z nowości w SDK.

Warto przejrzeć, choć z doświadczenia wiem, że kod nie jest idealny i trudny w czytaniu, ale zdecydowanie prezentuje dużo nowości.


# Źródła wiedzy

## Strony

### raywenderlich.com
https://raywenderlich.com/android

Najlepiej dopracowane tutoriale w Internecie.

RayWenderlich.com to strona, która oferuje dużo kursów, tutoriali i książek. Znacząca część 
jest płatna, ale te które są darmowe też wyglądają świetnie i są bardzo dopracowane.


### Vogella Android Tutorials
http://www.vogella.com/tutorials/android.html

Znane źródło tutoriali opisujących popularne zagadnienia z zakresu programowania na Androida i nie tylko.


### SzkolaAndroida.pl
https://SzkolaAndroida.pl

Blog, który tworzę w wolnym czasie pomiędzy projektami i szkoleniami. Staram się przekazywać spostrzeżenia dotyczące tworzenia aplikacji, zwłaszcza od strony warsztatu programisty.

### Android Weekly
http://androidweekly.net/

Cotygodniowa porcja przydatnych zasobów dotyczących programowania na Androida, przebranych i zebranych w jednym miejscu. Nowe biblioteki, posty na blogach i filmy wideo. Istnieje możliwość przeglądania na stronie internetowej, lub zamówienie subskrypcji wprost do skrzynki email.

### MaterialUp
http://www.materialup.com/

Ładny katalog ładnych aplikacji. Celem MaterialUp jest prezentowanie dobrych przykładów implementacji stylu Material Design w aplikacjach. Są tu nie tylko aplikacje Android, ale także iOS, a nawet aplikacje Web. Dobre źródło inspiracji i benchmarków. Zawsze polecam swoim klientom, aby zobaczyli co mogą zyskać idąc w kierunku Material Design.

### Android Arsenal
https://android-arsenal.com/

Największy katalog bibliotek, narzędzi i przykładów na Androida. Z możliwością przeszukiwania wg. różnych kryteriów m.in. cena, rodzaj, zastosowanie. Można potraktować jako rozbudowaną wersję tego ebooka. Niestety liczba dostępnych elementów powoduje, że pomiędzy perełkami jest dużo słabych bibliotek.

Alternatywy: https://www.android-libs.com


### Fragmented Podcast
https://fragmentedpodcast.com

Lubie podcasty, bo dają szansę zdobywać wiedzę, gdy jadę samochodem, albo jestem na siłowni. Spośród podcastów o Androidzie zdecydowanie wyróżnia się Fragmented.

Dużo wiedzy, aktualne tematy i znani goście sprawiają, że warto mu poświęcić kilkadziesiąt minut. 

{pagebreak}

## Kanały YouTube
Dla tych, którzy wolą oglądać wideo, zamiast czytać istnieje kilka kanałów, które warto dodać do swoich subskrybcji na YouTube, aby na bieżąco dostawać powiadomienia.

### SzkoleniaAndroid.pl - YouTube
https://www.youtube.com/channel/UCQUuM6One5W6odx8dDJ8Vsw

I znów kryptoreklama. Początkowo umieszczałem kursy, chwilowo lądują tam głównie zapisy z moich prezentacji na różnych wydarzeniach. Szczerze zachęcam do subskrybcji.

### Android Developers
https://www.youtube.com/channel/UCVHFbqXqoYvEWM1Ddxl0QDg

Ważny kanał dla tych, którzy chcą wiedzieć co nowego Google tym razem dodał do Androida. Oficjalny kanał, na którym zespół programistów z Google informuje o zmianach, a także pokazuje najlepsze praktyki. Aktywny najbardziej po Google IO, gdy następują ogłoszenia nowych API i narzędzi.

{pagebreak}

## Książki

### The Busy Coder's Guide to Android Development
http://commonsware.com/Android/

{height:20%}
![](resources/images/guide_cover.png)


Nietypowa książka autorstwa Mark'a Murphy'ego. Dostępna jedynie w postaci 12-miesięcznej subskrypcji, w trakcie której otrzymujemy dostęp do aktualizacji książki - zwykle jest kilka rocznie. Jedyny tytuł, który mogę polecić z czystym sumieniem, ponieważ w każdym momencie jest aktualna. No i ta objętość: ponad 4000 stron (tak, cztery tysiące)!

# Warto śledzić

## Jake Wharton

| *Strona*  | http://jakewharton.com/               |
| *Twitter* | https://twitter.com/JakeWharton       |
| *GitHub*      | https://github.com/JakeWharton |

{width:10%, float: right}
![](resources/images/jake_wharton.png)

Człowiek-legenda. Twórca wielu z przytoczonych bibliotek. Autorytet w kwestii upraszczania kodu, korzystania z anotacji oraz SDK. Wcześniej tworzył biblioteki w Square, obecnie pomaga developerom w Google.

## Romain Guy

| *Strona*  | http://www.curious-creature.com/    |
| *Twitter* | https://twitter.com/romainguy       | 
| *GitHub*      | https://github.com/romainguy |

{width:10%, float: right}
![](resources/images/romain_guy.jpg)

Googler pracujący nad Androidem. Często prezentuje nowości związane z UI.

## Chris Banes

| *Strona*  | https://chris.banes.me/              |
| *Twitter* | https://twitter.com/chrisbanes       |
| *GitHub*      | https://github.com/chrisbanes |

{width:10%, float: right}
![](resources/images/chris_banes.jpg)

Googler odpowiedzialny za relacje z developerami. Twórca wielu elementów biblioteki zgodności m.in. AppCompat.

Często dzieli się na swoich profilach fragmentami kodów, realizujących konkretne zadania np. znikający Toolbar.

{pagebreak}

## Nick Butcher

{width:10%, float: right}
![](resources/images/nick_butcher.jpg)


| *Strona*  | http://www.curious-creature.com/      |
| *Twitter* | https://twitter.com/crafty            |
| *G+*      | https://github.com/nickbutcher |


Googler odpowiedzialny za relacje na styku design/development. Umieszcza bardzo fajne prezentacje i przykłady. Dużo udziela się na kanale YouTube Android Developers.


## Wojtek Kaliciński

{width:10%, float: right}
![](resources/images/wojtek.jpeg)


| *Strona*  | https://medium.com/@wkalicinski     |
| *Twitter* | https://twitter.com/wkalic         |
| *GitHub*      | https://github.com/wojtek-kalicinski |


Nasz człowiek w Google. Wojtek pełni tam rolę Android Developer Advocate, czyli odpowiada za komunikacje z developerami. Możesz go spotkać na prawie każdej liczącej się konferencji, gdzie zwykle opowiada o najnowszych narzędziach od Google albo dobrych praktykach.

## Mark Murphy

{width:10%, float: right}
![](resources/images/mark_murphy.jpg)


| *Strona*  | https://commonsware.com/mmurphy |
| *Twitter* | https://twitter.com/commonsguy  |
| *GitHub*      | https://github.com/commonsguy                               |


Twórca CommonsWare i autor książki "The Busy Coder’s Guide to Android Development". Znajduje się w Top 10 najbardziej aktywnych osób na StackOverflow. Jeśli szukasz odpowiedzi na pytanie o Androida, duża szansa, że to on odpowie. Twórca dużej ilości bibliotek i częsty speaker na popularnych konferencjach mobilnych.

# Reklama :)

## Zasubskrybuj kanał Szkolenia Android na YouTube
https://SzkoleniaAndroid.pl/youtube

## Śledź Sylwester Madej na Twitter
https://twitter.com/smdremedy

## A przede wszystkim czytaj bloga
https://SzkolaAndroida.pl
