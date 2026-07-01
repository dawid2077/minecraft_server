# Indeks pluginów

> Pełna lista wszystkich pluginów zainstalowanych na serwerze, z opisami, funkcjami i istotnymi uwagami konfiguracyjnymi.

---

## Rozgrywka i podstawy

### EssentialsX (2.22.0)

Kręgosłup funkcji rozgrywkowych serwera. Zapewnia ekosystem komend, z których gracze korzystają na co dzień.

**Zainstalowane moduły:**
- **EssentialsX** — Podstawowe komendy: domy, warp, kity, teleportacja, wiadomości, mail
- **EssentialsXChat** — Formatowanie czatu z kolorami i placeholderami
- **EssentialsXSpawn** — Zarządzanie punktem spawnu
- **EssentialsXProtect** — Ochrona przed griefingiem (logowanie stawiania bloków, strefy zastrzeżone)

**Kluczowe funkcje:**
- `/home` / `/sethome` — Ustawianie i teleportacja do osobistych domów
- `/tpa` / `/tpahere` / `/tpaccept` / `/tpdeny` — System próśb o teleportację
- `/spawn` — Teleportacja do spawnu świata
- `/kit tools` — Startowy zestaw narzędzi (opóźnienie: 10s)
- `/back` — Powrót do ostatniego miejsca śmierci
- `/msg` / `/reply` — Prywatne wiadomości
- `/mail` — Wiadomości offline
- `/rules` — Wyświetlenie zasad serwera
- `/motd` — Wiadomość powitalna serwera

---

### VeinMiner (2.4.0)

Umożliwia efektywne wydobywanie całych żył rud jednym uderzeniem. Aktywowany przez skradanie się podczas kopania.

- **Aktywacja:** Skradanie (konfigurowalne)
- **Wzór:** Domyślny wzór żyły (połączone bloki tego samego typu)
- **Maks. rozmiar żyły:** 64 bloki
- **Doświadczenie i przedmioty:** Zbierane w miejscu źródłowym
- **Wyłączone tryby:** Kreatywny, Widz
- **Modyfikator głodu:** Każdy blok kosztuje 2.5 nasycenia jedzenia

---

### BetterSleeping (1.5)

Usprawnia mechanikę pomijania nocy. Tylko **1 gracz** musi spać, aby pominąć noc, co czyni to praktycznym przy małej liczbie graczy.

- **Gracze potrzebni do spania:** 1
- Działa dla dowolnej liczby graczy online

---

### SimpleScore (4.2.0)

Konfigurowalna tablica wyników wyświetlana po prawej stronie ekranu gracza.

- **Częstotliwość aktualizacji:** Co tick (20x/sekundę)
- **Przetwarzanie asynchroniczne:** Włączone (zapobiega opóźnieniom)
- **Wsparcie wielu światów:** Różne tablice wyników mogą być skonfigurowane dla świata/wzorca regex

---

### TAB (6.1.0)

Personalizuje listę graczy TAB (klawisz TAB) z grupowaniem, sortowaniem i formatowaniem nazw.

- Formatowanie nazw graczy i wyświetlanie prefiksów/sufiksów
- Sortowanie oparte na grupach
- Personalizacja nagłówka/stopki
- (Konfiguracja jest zarządzana po stronie serwera — klient nie wymaga modyfikacji)

---

## Bezpieczeństwo i egzekwowanie

### AuthMe (6.0.0)

Obsługuje uwierzytelnianie graczy na serwerze w trybie offline.

- Gracze muszą zarejestrować się z hasłem przy pierwszym dołączeniu
- Kolejne logowania wymagają hasła w określonym czasie
- Chroni przed nieautoryzowanym dostępem na nieuwierzytelnionym serwerze

---

### GrimAC (2.3.74)

Anty-cheat pluginu, który wykrywa i blokuje nieuczciwe przewagi.

- **Kontrole ruchu:** Szybkość, latanie, timer, NoFall itp.
- **Kontrole walki:** KillAura, Reach, AutoClicker
- **Kontrole eksperymentalne:** Włączone
- **Setbacki:** Agresywne — gracze przyłapani na oszukiwaniu są szybko cofani do bezpiecznej pozycji

---

### CombatLogX (11.7.0)

Zapobiega wylogowywaniu się graczy w celu uniknięcia PvP.

- **Czas tagowania:** 10 sekund po zaatakowaniu/otrzymaniu obrażeń
- **Po combat-logu (wyjście podczas tagu):** Gracz umiera (przedmioty wypadają)
- **Powiązane zwierzęta:** Obrażenia oswojonych zwierząt są przypisywane właścicielowi
- **Śledzenie pocisków:** Strzały i pociski są powiązane ze strzelającym
- **Ignorowane pociski:** Jajka, perły Endu, śnieżki

---

### CoreProtect (22.4)

System logowania i rollbacku na poziomie bloków.

- Loguje wszystkie umieszczania, niszczenia i interakcje bloków
- Obsługuje rollback akcji graczy (obszar lub konkretny gracz)
- Narzędzie do inspekcji, kto umieścił/zniszczył dany blok
- Niezbędny do odzyskiwania po griefingu

---

### EssentialsXProtect (2.22.0)

Dodatkowe zabezpieczenia przed griefingiem dołączone do EssentialsX.

- Czarna lista stawianych bloków
- Ochrona przed eksplozjami
- Sprawdzanie permisji budowania powiązane z systemem permisji

---

## Zarządzanie serwerem

### LuckPerms (5.5.58)

Zaawansowany system zarządzania permisjami.

- Dziedziczenie permisji oparte na grupach
- Permisje świadome kontekstu (świat, serwer itp.)
- Tracki (zestawy permisji, które można stosować sekwencyjnie)
- Przechowywanie: Baza danych H2 (lokalna, bez zewnętrznej bazy)
- Kontekst serwera: Globalny (permisje dotyczą wszystkich światów)

### Maintenance (5.1.0)

Przełączanie trybu konserwacji w celu blokowania połączeń podczas aktualizacji lub rozwiązywania problemów.

- **Przełączanie:** `/maintenance on` / `/maintenance off`
- **Niestandardowy MOTD:** Zmienia się, gdy konserwacja jest aktywna
- **Wiadomość kick:** Konfigurowalny powód rozłączenia
- **Język:** Polski (zlokalizowany dla docelowej grupy odbiorców)

### AdvancedServerList (5.8.0)

Personalizuje odpowiedź ping listy serwerów wyświetlaną w menu multiplayer.

- Niestandardowy MOTD z kolorami i formatowaniem
- Konfiguracja wyświetlania liczby graczy
- Wiadomości najechania na liczbę graczy
- Obsługa favicon

### CountryBlock

Plugin ograniczenia geograficznego.

- **Tryb:** Zezwól (tylko wymienione kraje mogą dołączyć)
- **Dozwolone:** Polska (PL)
- **Wykrywanie VPN:** Włączone — blokuje połączenia z VPN/proxy
- **Wiadomość kick:** Gracze zablokowani widzą komunikat o ograniczeniu krajowym

---

## Narzędzia i udogodnienia

### PlaceholderAPI (2.12.2)

Dostarcza stringi zastępcze jak `%player_name%`, `%online_players%`, które inne pluginy mogą używać w wiadomościach, tablicach wyników i listach TAB.

**Pluginy używające PlaceholderAPI na tym serwerze:**
- SimpleScore
- TAB
- EssentialsXChat
- DecentHolograms (jeśli skonfigurowane)

---

### DecentHolograms (2.10.1)

Tworzy pływające tekstowe hologramy w świecie.

- Używane do wyświetlania informacji (info o spawnie, zasady, ogłoszenia)
- Obsługuje widoczność dla konkretnego gracza
- Może używać placeholderów PlaceholderAPI

---

### SkinsRestorer

Przywraca skórki graczy w trybie offline. Ponieważ serwer nie łączy się z serwerami autoryzacyjnymi Mojanga, ten plugin pobiera i aplikuje skórki z alternatywnego źródła.

---

### spark

Profiler wydajności i narzędzie metryk.

- Profilowanie CPU
- Śledzenie encji i tile entity
- Monitorowanie TPS (ticków na sekundę)
- Analiza pamięci
- Dostępne w grze przez `/spark`

---

### BlueMap (5.12)

Żywa mapa 3D online renderująca świat w przeglądarce.

- **Dostęp:** `http://<ip-serwera>:8100`
- Renderuje teren, budynki i znaczniki graczy
- Aktualizuje się w czasie rzeczywistym wraz ze zmianami świata
- Wersja 5.12-paper (kompatybilna z Purpur 1.21.7)

---

### ViaVersion (5.10.0)

Pozwala klientom z różnych wersji Minecrafta łączyć się z serwerem 1.21.7.

- Wstecznie kompatybilny — starsi klienci mogą dołączyć
- Tłumaczy protokół między wersjami bezproblemowo

---

## Świat i środowisko

### Chunky (1.5.3)

Narzędzie do pre-generacji świata, które generuje chunki bez konieczności eksploracji przez graczy.

- **Promień:** 2000 bloków (overworld)
- **Wymiary:** Tylko Overworld (Nether/End wyłączone)
- **Funkcja:** Pre-generuje cały teren do granicy świata
- **Sprawdzenie statusu:** `/chunky progress` (konsola serwera)
- Działa jako asynchroniczne zadanie w tle

---

### UltimateAirdrops (2.1.0)

Okresowe wydarzenia zrzutów, które spawnią skrzynie z zaopatrzeniem w losowych lokalizacjach.

- Zrzuty zawierają losowy łup
- Efekty wizualne oznaczają strefy lądowania
- Zachęca do eksploracji i rywalizacji o zasoby

---

## Integracja i dane

### DiscordSRV

Mostkuje czat w grze z kanałem Discord. (Wymaga tokena bota i konfiguracji ID kanału — obecnie oczekuje na konfigurację.)

---

## Ochrona i edycja świata

### WorldEdit (7.3.15)

Edytor świata w grze. Używany głównie do selekcji obszarów dla WorldGuard.

**Instalacja:** Ściągnięty z Modrinth, wymagany przez WorldGuard.

### WorldGuard (7.0.14)

Ochrona regionów i flagi.

**Regiony:**
- **spawn** — 50×50 bloków (od -25 do 25 w X/Z, od 0 do 320 w Y)

**Flagi regionu spawn:**
| Flaga | Wartość |
|---|---|
| `pvp` | `deny` |
| `block-break` | `deny` |
| `block-place` | `deny` |
| `use` | `deny` |

**OP bypass:** Wyłączony (`disable-bypass-by-default: true`) — ochrona działa na wszystkich, nawet na operatorów.

---

## Wsparcie dla uwierzytelniania

### PacketEvents (2.13.0)

Biblioteka do przechwytywania pakietów sieciowych. Zainstalowana wyłącznie dla AuthMe premium crypto verification.

**Zależności:** AuthMe (offline-mode bez proxy)

---

## Zmiany konfiguracyjne (2026-07-01)

### CombatLogX
- Anti-logout timer: 10s → 20s (`default-timer: 20`)
- **Glowing** expansion: wyłączony (config: `enabled: false`) — nie ma świecenia przez ściany
- **ActionBar** expansion: wyłączony (config: `enabled: false`)
- **MobTagger** expansion: mob-list = `[]` — tylko PvP taguje, moby nie

### EssentialsX
- Teleport delay: 0s → 10s
- `/back` — wyłączony (disabled-commands + luckperms negatywna perm)
- `essentials.enderchest` — dodany do grupy default (wszyscy gracze)

### TAB
- Scoreboard: włączony z datą, animacją, online count, rank, ping, world
- Tab list header/footer: czas, ping, memory, "Odwiedź autora dawidm.com", "Sponsor serwera: https://codeeurope.pl/"
- Animacja Welcome: 100 losowych powitań z "❤️ kochamy Ante i Kolczyńska"
- Vanish: `display-vanished-players-as-spectators: true`

### AuthMe
- Premium mode: włączony (`enablePremium: true`)
- Premium gracze (Mojang/Microsoft) logują się bez hasła
- Non-premium gracze wymagają rejestracji

### BetterSleeping
- Action bar: wyłączony (`enable-actionbar: false`)

### CoreProtect
- Baza danych: zresetowana (uszkodzona po masowych spawnach entity, 2026-07-01)
- Nowa baza: 204KB, czysta

### Whitelist
- Włączona, tylko 4 graczy: EnderMag0220, nuqe_bb, reaperq, Low_Death_Gaming
