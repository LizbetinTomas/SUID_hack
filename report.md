Využil jsem zranitelnost spojenou s PATH Hijacking u SUID binárky, která volala externí příkaz bez absolutní cesty.  
Vytvořil jsem vlastní binárku `date` v `/tmp` a upravil proměnnou PATH tak, aby byla načítána před systémovou verzí.  
Program se SUID bitem se spustil s efektivním UID root, což umožnilo spuštění mého kódu s root právy.  
Rozdíl mezi UID a EUID je v tom, že UID určuje skutečného uživatele, zatímco EUID určuje práva procesu při běhu.  
Ochrana by zahrnovala používání absolutních cest v kódu, sanitizaci PATH a odstranění SUID u nepotřebných binárek.
