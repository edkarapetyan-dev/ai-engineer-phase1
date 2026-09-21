# Predictions

| # | Command | My prediction | What actually happened | Right? |
| --- | --- | --- | --- | --- |
| 1 | which python3 — before creating any venv | Versions 3.14 | /Library/Frameworks/Python.framework/Versions/3.14/bin/python3 | partial |
| 2 | python3 -m venv .venv then ls -a | will create .venv folder in working directory and list content of curent directory | Edgars-MacBook:phase1 EK$ python3 -m venv .venv
Edgars-MacBook:phase1 EK$ ls -a
.			.venv
..			homework6_venv.md |  |
| 3 | ~/ai-engineer/phase1/.venv/bin/python3 | source .venv/bin/activate
(.venv) Edgars-MacBook:phase1 EK$ which python3
/Users/EK/ai-engineer/phase1/.venv/bin/python3 | --- | --- |
| 4 | python3 -m pip list | will list the libraries which exist in the .venv folder | (.venv) Edgars-MacBook:phase1 EK$ python3 -m pip list
Package Version
------- -------
pip     26.2.1 |  |
| 5 | python3 ~/ai-engineer/phase0/ask.py | will fail, python complains, что не нахдены библиотеки или не удалось их найти/импортировать, line 2 - from dotenv import load_dotenv, Traceback Стадия 4 | --- | --- |
| 6 |deactivate
which python3 | /Library/Frameworks/Python.framework/Versions/3.14/bin/python3.  Команда deactivate удаляет путь .venv/bin из переменной PATH, возвращая PATH к его исходному состоянию. deactivate nothing removes from my disk. | Edgars-MacBook:phase1 EK$ which python3
/Library/Frameworks/Python.framework/Versions/3.14/bin/python3
Edgars-MacBook:phase1 EK$  | --- |
| 7 | deactivate then which python3 | /Library/Frameworks/Python.framework/Versions/3.14/bin/python3.  Команда deactivate удаляет путь .venv/bin из переменной PATH, возвращая PATH к его исходному состоянию. deactivate nothing removes from my disk. | | |
| 8 | cd ~/ai-engineer/phase1
source .venv/bin/activate
which python3 | Prediction: /Users/EK/ai-engineer/phase1/.venv/bin/python3
Команда deactivate удаляет путь .venv/bin из переменной PATH, команда activate вернула .venv/bin в PAHT. | | |
| 9 | python3 -m pip install python-dotenv google-genai
python3 -m pip list | more than 25, because we did not installed google-genai than | 27 — 26 installed now, plus pip itself | |

