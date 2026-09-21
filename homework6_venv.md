# Session Predictions

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


### HOMWWORK 7

**Step 1** — Test the recipe

cd ~/ai-engineer/phase1
python3 -m venv /tmp/venvtest
/tmp/venvtest/bin/python3 -m pip install -r requirements.txt
/tmp/venvtest/bin/python3 ~/ai-engineer/phase0/ask.py

Before you run the last line, write one prediction: will ask.py work from this environment, and why?
- Да, скрипт сработает, потому что прямой вызов /tmp/venvtest/bin/python3 использует виртуальное окружение /tmp/venvtest (и его библиотеки) напрямую, без необходимости запускать source activate.


Edgars-MacBook:~ EK$ cd ~/ai-engineer/phase1
Edgars-MacBook:phase1 EK$ python3 -m venv /tmp/venvtest
Edgars-MacBook:phase1 EK$ ls /tmp/venvtest
bin		include		lib		pyvenv.cfg
Edgars-MacBook:phase1 EK$ /tmp/venvtest/bin/python3 -m pip install -r requirements.txt
Collecting annotated-types==0.8.0 (from -r requirements.txt (line 1))
  Using cached annotated_types-0.8.0-py3-none-any.whl.metadata (15 kB)
Collecting anyio==4.15.1 (from -r requirements.txt (line 2))
  Using cached anyio-4.15.1-py3-none-any.whl.metadata (4.7 kB)
Collecting certifi==2026.7.22 (from -r requirements.txt (line 3))
  Using cached certifi-2026.7.22-py3-none-any.whl.metadata (2.5 kB)
Collecting cffi==2.1.1 (from -r requirements.txt (line 4))
  Using cached cffi-2.1.1-cp314-cp314-macosx_11_0_arm64.whl.metadata (2.5 kB)
Collecting charset-normalizer==3.5.1 (from -r requirements.txt (line 5))
  Using cached charset_normalizer-3.5.1-cp314-cp314-macosx_10_15_universal2.whl.metadata (45 kB)
Collecting cryptography==50.0.1 (from -r requirements.txt (line 6))
  Using cached cryptography-50.0.1-cp311-abi3-macosx_11_0_arm64.whl.metadata (4.3 kB)
Collecting distro==1.9.0 (from -r requirements.txt (line 7))
  Using cached distro-1.9.0-py3-none-any.whl.metadata (6.8 kB)
Collecting google-auth==2.58.0 (from -r requirements.txt (line 8))
  Using cached google_auth-2.58.0-py3-none-any.whl.metadata (6.0 kB)
Collecting google-genai==2.24.0 (from -r requirements.txt (line 9))
  Using cached google_genai-2.24.0-py3-none-any.whl.metadata (56 kB)
Collecting h11==0.16.0 (from -r requirements.txt (line 10))
  Using cached h11-0.16.0-py3-none-any.whl.metadata (8.3 kB)
Collecting httpcore==1.0.9 (from -r requirements.txt (line 11))
  Using cached httpcore-1.0.9-py3-none-any.whl.metadata (21 kB)
Collecting httpx==0.28.1 (from -r requirements.txt (line 12))
  Using cached httpx-0.28.1-py3-none-any.whl.metadata (7.1 kB)
Collecting idna==3.20 (from -r requirements.txt (line 13))
  Using cached idna-3.20-py3-none-any.whl.metadata (7.2 kB)
Collecting pyasn1==0.6.4 (from -r requirements.txt (line 14))
  Using cached pyasn1-0.6.4-py3-none-any.whl.metadata (8.4 kB)
Collecting pyasn1_modules==0.4.2 (from -r requirements.txt (line 15))
  Using cached pyasn1_modules-0.4.2-py3-none-any.whl.metadata (3.5 kB)
Collecting pycparser==3.0 (from -r requirements.txt (line 16))
  Using cached pycparser-3.0-py3-none-any.whl.metadata (8.2 kB)
Collecting pydantic==2.13.5 (from -r requirements.txt (line 17))
  Using cached pydantic-2.13.5-py3-none-any.whl.metadata (110 kB)
Collecting pydantic_core==2.46.5 (from -r requirements.txt (line 18))
  Using cached pydantic_core-2.46.5-cp314-cp314-macosx_11_0_arm64.whl.metadata (6.6 kB)
Collecting python-dotenv==1.2.3 (from -r requirements.txt (line 19))
  Using cached python_dotenv-1.2.3-py3-none-any.whl.metadata (29 kB)
Collecting requests==2.34.2 (from -r requirements.txt (line 20))
  Using cached requests-2.34.2-py3-none-any.whl.metadata (4.8 kB)
Collecting sniffio==1.3.1 (from -r requirements.txt (line 21))
  Using cached sniffio-1.3.1-py3-none-any.whl.metadata (3.9 kB)
Collecting tenacity==9.1.4 (from -r requirements.txt (line 22))
  Using cached tenacity-9.1.4-py3-none-any.whl.metadata (1.2 kB)
Collecting typing-inspection==0.4.4 (from -r requirements.txt (line 23))
  Using cached typing_inspection-0.4.4-py3-none-any.whl.metadata (2.6 kB)
Collecting typing_extensions==4.16.0 (from -r requirements.txt (line 24))
  Using cached typing_extensions-4.16.0-py3-none-any.whl.metadata (3.3 kB)
Collecting urllib3==2.8.0 (from -r requirements.txt (line 25))
  Using cached urllib3-2.8.0-py3-none-any.whl.metadata (7.4 kB)
Collecting websockets==16.1.1 (from -r requirements.txt (line 26))
  Using cached websockets-16.1.1-cp314-cp314-macosx_11_0_arm64.whl.metadata (6.8 kB)
Using cached annotated_types-0.8.0-py3-none-any.whl (13 kB)
Using cached anyio-4.15.1-py3-none-any.whl (132 kB)
Using cached certifi-2026.7.22-py3-none-any.whl (136 kB)
Using cached cffi-2.1.1-cp314-cp314-macosx_11_0_arm64.whl (184 kB)
Using cached charset_normalizer-3.5.1-cp314-cp314-macosx_10_15_universal2.whl (341 kB)
Using cached cryptography-50.0.1-cp311-abi3-macosx_11_0_arm64.whl (4.0 MB)
Using cached distro-1.9.0-py3-none-any.whl (20 kB)
Using cached google_auth-2.58.0-py3-none-any.whl (262 kB)
Using cached google_genai-2.24.0-py3-none-any.whl (1.1 MB)
Using cached httpx-0.28.1-py3-none-any.whl (73 kB)
Using cached httpcore-1.0.9-py3-none-any.whl (78 kB)
Using cached pydantic-2.13.5-py3-none-any.whl (472 kB)
Using cached requests-2.34.2-py3-none-any.whl (73 kB)
Using cached idna-3.20-py3-none-any.whl (69 kB)
Using cached tenacity-9.1.4-py3-none-any.whl (28 kB)
Using cached typing_extensions-4.16.0-py3-none-any.whl (45 kB)
Using cached urllib3-2.8.0-py3-none-any.whl (135 kB)
Using cached websockets-16.1.1-cp314-cp314-macosx_11_0_arm64.whl (177 kB)
Using cached h11-0.16.0-py3-none-any.whl (37 kB)
Using cached pyasn1-0.6.4-py3-none-any.whl (84 kB)
Using cached pyasn1_modules-0.4.2-py3-none-any.whl (181 kB)
Using cached pycparser-3.0-py3-none-any.whl (48 kB)
Using cached pydantic_core-2.46.5-cp314-cp314-macosx_11_0_arm64.whl (1.9 MB)
Using cached python_dotenv-1.2.3-py3-none-any.whl (22 kB)
Using cached sniffio-1.3.1-py3-none-any.whl (10 kB)
Using cached typing_inspection-0.4.4-py3-none-any.whl (14 kB)
Installing collected packages: websockets, urllib3, typing_extensions, tenacity, sniffio, python-dotenv, pycparser, pyasn1, idna, h11, distro, charset-normalizer, certifi, annotated-types, typing-inspection, requests, pydantic_core, pyasn1_modules, httpcore, cffi, anyio, pydantic, httpx, cryptography, google-auth, google-genai
Successfully installed annotated-types-0.8.0 anyio-4.15.1 certifi-2026.7.22 cffi-2.1.1 charset-normalizer-3.5.1 cryptography-50.0.1 distro-1.9.0 google-auth-2.58.0 google-genai-2.24.0 h11-0.16.0 httpcore-1.0.9 httpx-0.28.1 idna-3.20 pyasn1-0.6.4 pyasn1_modules-0.4.2 pycparser-3.0 pydantic-2.13.5 pydantic_core-2.46.5 python-dotenv-1.2.3 requests-2.34.2 sniffio-1.3.1 tenacity-9.1.4 typing-inspection-0.4.4 typing_extensions-4.16.0 urllib3-2.8.0 websockets-16.1.1
Edgars-MacBook:phase1 EK$ /tmp/venvtest/bin/python3 ~/ai-engineer/phase0/ask.py
Direct use of automatic function calling (AFC) in Models.generate_content is not recommended. Instead, we recommend to use AFC in Chat.send_message. Similarly, direct use of AFC in Models.generate_content_stream is not recommended. Instead, we recommend to use AFC in Chat.send_message_stream.
Exactly three words.


**Step 2** — Write README.md in phase1

Создал README.md

3–5 sentences, in Russian if you like, on what requirements.txt is for.
- Файл requirements.txt содержит список всех внешних зависимостей проекта и их зафиксированные версии. Он позволяет быстро воссоздать изолированное виртуальное окружение с нужными библиотеками. Это гарантирует совпадение версий пакетов при разработке, хотя поведение может зависеть от версии самого Python и операционной системы.



**Step 3** - Commit and push

(.venv) Edgars-MacBook:phase1 EK$ git status
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   homework6_venv.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	README.md

no changes added to commit (use "git add" and/or "git commit -a")
(.venv) Edgars-MacBook:phase1 EK$ git ls-files
.gitignore
homework6_venv.md
requirements.txt



https://github.com/edkarapetyan-dev/ai-engineer-phase1.git

git commit -m "add README.md file for virtual enviromnet version and homework6_vnv.md"