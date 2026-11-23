# Football OS i sen z Apple Watch

Apple Watch zapisuje sen w aplikacji Zdrowie na iPhonie. Skrót pobiera odcinki snu z ostatnich siedmiu dni i wysyła je do uprawnionej instancji Football OS. Zalogowany użytkownik sprawdza wynik w sekcji **Regeneracja → Sen i zmęczenie**.

Ręczny odczyt i import potwierdzono na prywatnej instancji oraz jednym zestawie iPhone + Apple Watch. Automatyzacja w tle, drugi zestaw urządzeń i inne konto wymagają osobnego sprawdzenia. [Śledzenie snu na Apple Watch](https://support.apple.com/pl-pl/108906)

## Dostęp do Football OS

Pobranie pliku nie daje dostępu do prywatnej aplikacji. Potrzebujesz działającej instancji Football OS, dostępu do niej na własnym koncie i zatwierdzonej przez operatora ścieżki połączenia urządzenia.

Szablon jest przeznaczony dla operatora własnej instancji. Prywatny ChatGPT Sites wymaga poświadczenia witryny. Jest ono szersze niż indywidualne uprawnienie do importu i nie powinno być przekazywane użytkownikom wspólnej instancji. Zaproszeni użytkownicy potrzebują osobnego mechanizmu parowania urządzenia. [Dokumentacja ChatGPT Sites](https://learn.chatgpt.com/docs/sites/data-and-connections#call-a-private-site-with-a-siwc-bypass-token)

## Pierwsza próba przez operatora własnej instancji

1. Sprawdź w **Zdrowie → Przeglądaj → Sen**, czy ostatnia noc ma zmierzone odcinki snu.
2. W Football OS wejdź w **Więcej → Aplikacja i dane → Apple Zdrowie** i pobierz token zapisu snu swojego konta. Utworzenie nowego tokenu zastępuje poprzedni.
3. W zaufanej, podpisanej wersji Skrótu zweryfikuj właściwy adres HTTPS z końcówką `/api/integrations/apple-health/sleep`. Szablon do przeglądu ma przykładowy adres `football-os.example.invalid` i zatrzymuje się na nim przed odczytem oraz pytaniami o klucze. Szablon przyjmuje publiczną nazwę DNS hosta i standardowy port HTTPS.
4. Uruchom na odblokowanym iPhonie. Wpisz lokalnie istniejące poświadczenie wyłącznie własnego Sites oraz indywidualny token importu Football OS. Zgódź się na odczyt Snu i połączenie z własną, sprawdzoną domeną. Ten szablon pyta o poświadczenia przy każdym uruchomieniu i nie zapisuje ich do pliku.
5. Potwierdź **Import snu zakończony**, godzinę **Ostatni odebrany import** w ustawieniach i właściwą noc w **Regeneracja → Sen i zmęczenie**.

Dane wysyłane przez szablon obejmują przedziały odczytanych faz, ograniczoną etykietę źródła, czas obserwacji oraz nazwę strefy. Strefa przykładowa w akcji budującej JSON to `Europe/Warsaw`; operator dopasowuje ją do swojego zastosowania. Przy braku internetu ponów na urządzeniu po odzyskaniu połączenia. Nie przekazuj tokenów w zgłoszeniach, zrzutach, adresach ani plikach do udostępniania.

Automatyzacja systemowa jest osobnym krokiem. Wariant z ręcznym podawaniem poświadczeń nie nadaje się do bezobsługowej pracy. Plik w paczce przeglądowej jest niepodpisanym szablonem i nie stanowi wydania do pobrania na cudzym iPhonie. Ewentualne wydanie podpisane wymaga weryfikacji na drugim urządzeniu oraz zatwierdzenia treści przed publikacją. [Udostępnianie Skrótów](https://support.apple.com/en-gb/guide/shortcuts/apdf01f8c054/ios)
