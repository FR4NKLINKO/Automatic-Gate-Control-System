🟢 SMARTGATE
Inteligentny system automatycznego sterowania bramą

<p align="center">
<img src="https://img.shields.io/badge/ARDUINO-UNO-00979D?style=for-the-badge&logo=arduino&logoColor=white" />
<img src="https://img.shields.io/badge/LANGUAGE-C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" />
<img src="https://img.shields.io/badge/PROJECT-ELECTRONICS-22C55E?style=for-the-badge" />
<img src="https://img.shields.io/badge/STATUS-IN%20DEVELOPMENT-orange?style=for-the-badge" />
</p>

<p align="center">
<b>⚡ Automatyka • 🛡️ Bezpieczeństwo • 🎮 Zdalne sterowanie</b>
</p>

📌 O projekcie

SmartGate to projekt inteligentnego systemu automatycznego sterowania bramą dwuskrzydłową, zrealizowany z wykorzystaniem mikrokontrolera Arduino UNO.

Urządzenie umożliwia zdalne otwieranie, zamykanie oraz zatrzymywanie bramy za pomocą pilota na podczerwień. Dodatkowo zastosowany czujnik ruchu PIR monitoruje otoczenie i zatrzymuje pracę mechanizmu w przypadku wykrycia ruchu podczas przemieszczania się bramy.

System wykorzystuje dwa serwomechanizmy, które poruszają się synchronicznie, zapewniając płynne otwieranie i zamykanie obu skrzydeł.

💡 Głównym założeniem projektu jest stworzenie prostego, funkcjonalnego i możliwego do rozbudowy systemu automatyki bramowej.
🖼️ Schemat projektu

<p align="center">
<i>Schemat połączeń elektronicznych projektu SmartGate.</i>
</p>

⚙️ Najważniejsze funkcje
Funkcja	Opis
🎮 Sterowanie IR	Obsługa systemu za pomocą pilota
🚪 Automatyczne otwieranie	Płynne otwieranie dwóch skrzydeł
🔒 Automatyczne zamykanie	Powrót bramy do pozycji zamkniętej
🛑 Zatrzymywanie	Możliwość zatrzymania bramy w dowolnym momencie ruchu
🔄 Wznawianie ruchu	Kontynuowanie ruchu w wybranym kierunku
👁️ Detekcja ruchu	Wykrywanie ruchu za pomocą czujnika PIR
💡 Sygnalizacja LED	Informacja o aktualnym ruchu bramy
🔌 Wykorzystane komponenty
Komponent	Ilość	Zastosowanie
Arduino UNO	1	Jednostka sterująca
Serwomechanizm SG90	2	Sterowanie skrzydłami bramy
Czujnik PIR	1	Detekcja ruchu
Odbiornik IR	1	Odbiór sygnałów z pilota
Pilot IR	1	Zdalne sterowanie
Dioda LED	1	Sygnalizacja ruchu
Rezystor	1	Ograniczenie prądu diody
Przewody połączeniowe	-	Połączenia układu
📍 Konfiguracja pinów Arduino
Element	Pin Arduino
Serwomechanizm 1	D3
Serwomechanizm 2	D5
Odbiornik podczerwieni	D10
Dioda LED	D12
Czujnik ruchu PIR	D4
🧠 Logika działania systemu

System wykorzystuje mechanizm maszyny stanów (State Machine), który odpowiada za kontrolowanie aktualnego położenia bramy i wykonywanych operacji.

🔄 Dostępne stany
Stan	Nazwa	Opis
0	ZAMKNIĘTA	Brama znajduje się w pozycji zamkniętej
1	OTWARTA	Brama znajduje się w pozycji otwartej
4	OTWIERANIE	Trwa proces otwierania
5	ZAMYKANIE	Trwa proces zamykania
6	ZATRZYMANIE	Brama zatrzymana w aktualnym położeniu
🎮 Sterowanie pilotem

Do obsługi systemu wykorzystywany jest przycisk POWER na pilocie IR.

Aktualna sytuacja	Reakcja systemu
Brama zamknięta	Rozpoczęcie otwierania
Brama otwarta	Rozpoczęcie zamykania
Brama w ruchu	Zatrzymanie
Brama zatrzymana	Wznowienie ruchu
👁️ System wykrywania ruchu

Czujnik PIR stale monitoruje otoczenie bramy.

Jeżeli podczas ruchu bramy czujnik wykryje obecność lub ruch, system:

Odczytuje sygnał z czujnika PIR.
Zatrzymuje oba serwomechanizmy.
Zapamiętuje aktualne położenie skrzydeł.
Przechodzi do stanu zatrzymania.
📐 Pozycje serwomechanizmów
Pozycja bramy	Serwo 1	Serwo 2
🔒 Zamknięta	0°	180°
🟢 Otwarta	90°	90°
🛑 Zatrzymana	Aktualna pozycja	Aktualna pozycja

Oba serwomechanizmy wykonują ruch synchronicznie, zmieniając położenie o jeden stopień co około 15 ms.

💻 Wykorzystane technologie
Arduino C++ – logika sterowania.
Servo.h – obsługa serwomechanizmów.
IRremote.hpp – komunikacja z pilotem IR.
PIR Sensor – detekcja ruchu.
State Machine – zarządzanie stanami systemu.
📦 Wymagane biblioteki

Przed uruchomieniem programu należy zainstalować:

Servo
IRremote

Biblioteki można znaleźć w menedżerze bibliotek Arduino IDE.

🚀 Uruchomienie projektu
Pobierz repozytorium:
bash
git clone https://github.com/TWOJ-LOGIN/SmartGate.git

Otwórz plik projektu w Arduino IDE.
Zainstaluj wymagane biblioteki.
Podłącz komponenty zgodnie ze schematem.
Wybierz płytkę Arduino UNO.
Wgraj program do mikrokontrolera.
Uruchom układ i przetestuj sterowanie pilotem.
📁 Struktura repozytorium
text
SmartGate/
│
├── 📂 images/
│   ├── circuit.png
│   └── prototype.jpg
│
├── 📄 SmartGate.ino
└── 📄 README.md

🔮 Możliwości rozwoju

Projekt można rozbudować o dodatkowe funkcjonalności:

📱 Sterowanie przez Bluetooth.
🌐 Sterowanie przez Wi-Fi.
⏱️ Automatyczne zamykanie po określonym czasie.
🖥️ Wyświetlacz LCD lub OLED prezentujący stan systemu.
⚙️ Regulacja prędkości serwomechanizmów.
🚨 Dodatkowy system wykrywania przeszkód.
🔐 Zabezpieczenie dostępu do sterowania.
🛡️ Uwagi dotyczące bezpieczeństwa

Projekt ma charakter edukacyjny i demonstracyjny. Czujnik PIR nie zastępuje certyfikowanego systemu zabezpieczenia bramy przed przygnieceniem lub uderzeniem.

Przy zastosowaniu rzeczywistej bramy konieczne jest wykorzystanie odpowiednich zabezpieczeń, czujników przeszkód oraz niezależnego układu awaryjnego zatrzymania.

👨‍💻 Autor

Projekt wykonany w ramach nauki programowania mikrokontrolerów Arduino oraz praktycznego zastosowania elektroniki i automatyki.


<h3 align="center">🟢 SMARTGATE</h3>
<p align="center"><i>Przyszłość automatyki zaczyna się od prostych rozwiązań.</i></p>
