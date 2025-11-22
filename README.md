# Поиск доменных имен

Открыть страницу в Chrome, нажать F12 - Перейти во вкладку console, прописать команду allow pasting , а не скопировать (так не работает)

Затем следующую команду скопировать и вставить в console

> _window.domains = [...new Set(performance.getEntriesByType('resource').map(r => (new URL(r.name)).hostname))];_
> _console.log(domains);_

Полученные домены скопировать и вставить в https://rockblack.pro/ip-address

# Searching for domain names

Open page in Chrome, press F12, go to the console tab, enter the command allow pasting instead of copying (this doesn't work)

Then copy and paste the following command into the console

> _window.domains = [...new Set(performance.getEntriesByType('resource').map(r => (new URL(r.name)).hostname))];_
> _console.log(domains);_

Copy the obtained domains and paste them into https://rockblack.pro/ip-address
