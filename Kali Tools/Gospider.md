
gospider -s [http://vulnnet.thm](http://vulnnet.thm) -c 10 -d 0 -w -t 10 — robots -a -r -v

## 📚 Breakdown of Flags and Options:

|**Option**|**Meaning**|
|---|---|
|`-s http://vulnnet.thm`|**Start URL** – The target domain to spider.|
|`-c 10`|**Concurrency** – Run 10 threads to crawl URLs in parallel (speeds up scanning).|
|`-d 0`|**Max Depth** – Crawl depth of 0, which means **only the given URL** is crawled (no sub-pages).|
|`-w`|**Enable Wordlist Output** – Extract words and paths found in the HTML/JS and output them (useful for fuzzing).|
|`-t 10`|**Threads per site** – Use 10 threads for each host/domain.|
|`--robots`|**Check and follow `robots.txt`** – Tries to find and parse `/robots.txt` (can reveal hidden or restricted paths).|
|`-a`|**Include subdomains** – Crawl subdomains found in the page (like `admin.vulnnet.thm`, etc).|
|`-r`|**Follow redirects** – Follows HTTP 3xx redirects while crawling.|
|`-v`|**Verbose output** – Print detailed logs of what GoSpider is doing.|


