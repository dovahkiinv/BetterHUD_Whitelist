# `alpha/` — lista testerów (roster alpha)

Tu siedzi lista graczy dopuszczonych do alpha testu: **SteamID64 + nick**.

* `alpha/whitelist.json` — jedyne źródło prawdy. Wpisy dodaje właściciel repo (albo przez PR po zgłoszeniu
  w Issues: „Alpha access (SteamID64 + nick)”).
* `../tools/alpha_roster.py` zamienia JSON na `src/BetterHUD.DR3/AlphaRoster.Generated.cs` (kod C#),
  dzięki czemu lista jedzie **w środku DLL** — mod nie łączy się z internetem.
  Skrypt uruchamia `build.ps1` i CI; można też ręcznie: `python3 tools/alpha_roster.py`.
* Testy repo sprawdzają, czy plik `.cs` zgadza się z JSON-em (`python3 tools/alpha_roster.py --check`).

Numer to **SteamID64 konta** (17 cyfr, zaczyna się od `7656119`, np. `76561198227702608`).
Wpis bez poprawnego numeru zatrzyma budowanie z komunikatem, którego wpisu dotyczy.

Jak sprawdzić w grze, czy lista Cię zna i jak działa blokada dostępu: [`../docs/ALPHA.pl.md`](../docs/ALPHA.pl.md).
