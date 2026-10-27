# Wszystkie nowości w przebudowanej aplikacji Claude Code

Pełna lista z mojej rolki. W październiku 2026 Anthropic przebudował zakładkę Code w aplikacji desktopowej Claude (Claude Desktop v2.42304.0, 15.10.2026).

Przy każdej funkcji jest: co to jest, jak ją włączyć i gdzie jest haczyk. Wszystko sprawdziłem w dokumentacji i changelogu Anthropic; linki są na dole. 🇬🇧 English: [README.md](README.md)

---

## Trzy z rolki

### 1. Side chaty: pytasz bez przerywania zadania
- **Co to:** czat obok sesji, który czyta cały główny wątek do tego momentu. Nic, o co tam zapytasz, nie wraca do głównej rozmowy.
- **Jak:** `Cmd+;` na macOS, `Ctrl+;` na Windows albo wpisz `/btw` w polu wiadomości. Każdy side chat ma własną kartę.
- **Haczyk:** side chaty **nie są zapisywane**. Zamkniesz aplikację i znikają, więc skopiuj to, co ważne.

### 2. Projekty: jeden czat-koordynator prowadzi mały zespół
- **Co to:** jedna ciągła rozmowa, która zakłada osobny wątek na każde zadanie, pilnuje wszystkich i dostaje od nich raporty. Wątki mają wspólną pamięć projektu, a wątki w chmurze działają dalej po zamknięciu laptopa.
- **Dla kogo:** publiczna beta w planach Pro i Max. W Team i Enterprise jeszcze nie ma.
- **Haczyk:** projekty szybciej zużywają limit. Jest twardy limit 200 nowych wątków dziennie.
- **Wersja lokalna, czyli sesje zagnieżdżone.** W sesjach lokalnych i SSH Claude może zacząć zadanie w osobnej sesji. Ta sesja pojawia się w pasku bocznym pod oryginalną i do niej raportuje. W **Ustawienia › Claude Code** wybierasz, co ma się dziać, gdy prosisz o coś niezwiązanego z zadaniem.

### 3. `/skill-doctor`: znajdź skille, które zjadają kontekst
- **Co to:** każdy zainstalowany skill zajmuje kontekst **w każdej turze, nawet jeśli Claude go nigdy nie użyje**. `/skill-doctor` pokazuje, ile kosztuje każdy skill i jak często jest naprawdę używany, więc wiesz, co usunąć.
- **Jak:** wpisz `/skill-doctor`. Potrzebny jest Claude Code 2.1.252 lub nowszy; raport otwiera się w `/plugin` › Stats.
- Jeden twórca (Ben AI) obciął tak około 20 000 tokenów. To jego własny test, nie oficjalna liczba.

---

## Wszystko inne, co nowe

### Szyna sesji (karty obok czatu)
Po prawej stronie rozmowy są karty: środowisko, kontekst, konektory, pliki wynikowe, zmiany, serwery i zadania w tle. Kliknij prawym przyciskiem nagłówek karty, żeby wybrać, które karty mają być widoczne.
- **Karta kontekstu:** ile kontekstu jest zajęte i przez co.
- **Karta środowiska:** sesja lokalna czy w chmurze, plus przełącznik **Remote Control**, żeby kontynuować sesję z telefonu.

### Ramka z planem
Kiedy Claude pracuje, na końcu rozmowy jest ramka z jego planem, w której odhacza kolejne kroki. Po zakończeniu tury może pokazać krótkie podsumowanie z przyciskami do następnego kroku. Działa tylko w sesjach lokalnych i SSH.

### Sekcje
Sesje w pasku bocznym można grupować. Własne grupy nazywają się teraz sekcjami. Grupować można też według środowiska.

### Zapisane środowiska
Zapisujesz folder, hosta SSH, środowisko w chmurze albo maszynę Remote Control, a potem wybierasz je przy starcie sesji.

### Sesje, które rozmawiają ze sobą
Claude widzi Twoje pozostałe sesje w zakładce Code. Może przeczytać, co każda robiła, i przesyłać wiadomości między nimi. Wystarczy poprosić zwykłymi słowami, np. „powiedz sesji od płatności, że zmienił się schemat”. Widzi 20 ostatnio aktywnych sesji.

### Widok dzielony
Dwie sesje obok siebie. Przytrzymaj `Option` (macOS) albo `Alt` (Windows) i kliknij sesję, albo kliknij ją prawym przyciskiem › **Open in** › **Split view**. Ta funkcja nie jest z października, ale większość ludzi jej nie znalazła.

### Komendy, które warto znać
- `/output-style`: zmienia sposób odpowiadania, np. `/output-style concise`. Wbudowane style to Proactive, Concise, Explanatory i Learning, a aplikacja desktopowa umie napisać własny styl z opisu.
- `/doctor`: przegląd instalacji, ustawień, rozszerzeń i CLAUDE.md.
- `/doctor prompt-audit`: sprawdza pliki CLAUDE.md i skille pod kątem przestarzałych albo sprzecznych instrukcji. Uruchom ją, jeśli Twoja konfiguracja ma już kilka miesięcy.
- `/advisor`: tańszy model radzi się mocniejszego (Opus albo Fable) w kluczowych momentach. To funkcja eksperymentalna i działa tylko przez API Anthropic.

### Mody
Małe funkcje w TypeScripcie, które zmieniają działanie Claude Code. Mod może przepisać prompt, zanim trafi do modelu, zablokować albo przepisać wywołanie narzędzia, ukryć sekrety albo dodać własne panele i przyciski. Wbudowane `/diff` jest teraz modem. **Haczyk:** mody mają taki sam dostęp do Twojego komputera jak sam Claude Code, więc przeczytaj kod, zanim zainstalujesz cudzy mod.

### Docs, Slides, Design, Dashboards, Motion
- **Docs, Slides i Design** wyszły z bety i są dostępne w każdym planie, także darmowym.
- **Dashboards** (beta, plany płatne): kliknij dowolną liczbę, żeby zobaczyć zapytanie, z którego pochodzi. Każdy wykres pokazuje, kiedy dane były ostatnio odświeżone.
- **Motion** (beta): animowane filmy robione kodem, bez modelu wideo i bez ludzi wygenerowanych przez AI. Wpisz `/motion`. Dostępne **tylko w planach Team i Enterprise**.

---

## Czy przejść z Coworka do zakładki Code?
Tak uważa Ben i ja też: nowe funkcje trafiają najpierw do zakładki Code, i to nie jest narzędzie tylko dla programistów. Oficjalnie Cowork i czat łączą się w „jednego Claude'a”; zmiana wchodzi stopniowo w planach Pro i Max.

## Źródła (wszystkie oficjalne)
- Changelog Claude Desktop: https://claude.com/docs/cowork/changelog
- Dokumentacja aplikacji (side chaty, widok dzielony, środowiska, wiadomości między sesjami): https://code.claude.com/docs/en/desktop
- Projekty: https://code.claude.com/docs/en/claude-projects · https://claude.com/blog/projects-redesigned
- Skille, `/skill-doctor`, `/doctor`: https://code.claude.com/docs/en/skills
- Komendy i `/output-style`: https://code.claude.com/docs/en/commands
- `/advisor`: https://code.claude.com/docs/en/advisor
- Mody: https://claude.com/resources/articles/claude-code-mods
- Dashboards i Motion: https://claude.com/resources/articles/dashboards-and-motion
- Cowork is now Claude: https://claude.com/blog/cowork-is-now-claude

Na podstawie przeglądu Bena AI „Claude 2.0 is Insane”: https://youtu.be/J5EbL1UaqG8

---
Kris · [@kris.aiwpraktyce](https://www.tiktok.com/@kris.aiwpraktyce) na TikToku · [@aipractically](https://www.instagram.com/aipractically/) na Instagramie
