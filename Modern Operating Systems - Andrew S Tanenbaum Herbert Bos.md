---
title: Modern Operating Systems
subtitle: 
author: Andrew S. Tanenbaum, Herbert Bos
authors: Andrew S. Tanenbaum,Herbert Bos
category: Operating systems (Computers).
publisher: Prentice Hall
totalPage: 0
coverUrl: http://books.google.com/books/content?id=9gqnngEACAAJ&printsec=frontcover&img=1&zoom=1&source=gbs_api
coverSmallUrl: http://books.google.com/books/content?id=9gqnngEACAAJ&printsec=frontcover&img=1&zoom=5&source=gbs_api
publishDate: 2015
description: Modern Operating Systems is intended for introductory courses in Operating Systems in Computer Science, Computer Engineering, and Electrical Engineering programs.
link: https://books.google.com/books/about/Modern_Operating_Systems.html?hl=&id=9gqnngEACAAJ
previewLink: http://books.google.com.au/books?id=9gqnngEACAAJ&dq=9780137618873&hl=&as_pt=BOOKS&cd=1&source=gbs_api
isbn10: 013359162X
isbn13: 9780133591620
annotation-target: Resources/Textbooks/COMP3231/Modern Operating Systems.pdf
---


>%%
>```annotation-json
>{"created":"2024-02-23T07:50:24.349Z","updated":"2024-02-23T07:50:24.349Z","document":{"title":"MODERN OPERATING SYSTEMS, 5e","link":[{"href":"urn:x-pdf:d2fc41488974e845ac0370313ae095aa"},{"href":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf"}],"documentFingerprint":"d2fc41488974e845ac0370313ae095aa"},"uri":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf","target":[{"source":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf","selector":[{"type":"TextPositionSelector","start":396772,"end":396842},{"type":"TextQuoteSelector","exact":"aninteger variable to count the number of wakeups saved for future use","prefix":"Dijkstra (1965) suggested using ","suffix":". In his initialproposal,  a  ne"}]}]}
>```
>%%
>*%%PREFIX%%Dijkstra (1965) suggested using%%HIGHLIGHT%% ==aninteger variable to count the number of wakeups saved for future use== %%POSTFIX%%. In his initialproposal,  a  ne*
>%%LINK%%[[#^acdeofrd2t|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^acdeofrd2t


>%%
>```annotation-json
>{"created":"2024-02-23T07:50:37.416Z","updated":"2024-02-23T07:50:37.416Z","document":{"title":"MODERN OPERATING SYSTEMS, 5e","link":[{"href":"urn:x-pdf:d2fc41488974e845ac0370313ae095aa"},{"href":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf"}],"documentFingerprint":"d2fc41488974e845ac0370313ae095aa"},"uri":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf","target":[{"source":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf","selector":[{"type":"TextPositionSelector","start":396977,"end":397108},{"type":"TextQuoteSelector","exact":"semaphore could have the value 0, indicating that no wakeups were saved, or somepositive value if one or more wakeups were pending.","prefix":"30 PROCESSES AND THREADS CHAP. 2","suffix":"Dijkstra  proposed  having  two "}]}]}
>```
>%%
>*%%PREFIX%%30 PROCESSES AND THREADS CHAP. 2%%HIGHLIGHT%% ==semaphore could have the value 0, indicating that no wakeups were saved, or somepositive value if one or more wakeups were pending.== %%POSTFIX%%Dijkstra  proposed  having  two*
>%%LINK%%[[#^db13rcdbims|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^db13rcdbims


>%%
>```annotation-json
>{"created":"2024-02-23T07:50:59.056Z","updated":"2024-02-23T07:50:59.056Z","document":{"title":"MODERN OPERATING SYSTEMS, 5e","link":[{"href":"urn:x-pdf:d2fc41488974e845ac0370313ae095aa"},{"href":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf"}],"documentFingerprint":"d2fc41488974e845ac0370313ae095aa"},"uri":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf","target":[{"source":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf","selector":[{"type":"TextPositionSelector","start":397526,"end":397811},{"type":"TextQuoteSelector","exact":"Check-ing the value, changing it, and possibly going to sleep, are all done as a single, in-divisible atomic  action. It is guaranteed  that  once  a  semaphore  operation  hasstarted,  no  other  process  can  access  the  semaphore  until  the  operation  has  com-pleted or blocked.","prefix":"leting the down for the moment. ","suffix":" This atomicity is absolutely es"}]}]}
>```
>%%
>*%%PREFIX%%leting the down for the moment.%%HIGHLIGHT%% ==Check-ing the value, changing it, and possibly going to sleep, are all done as a single, in-divisible atomic  action. It is guaranteed  that  once  a  semaphore  operation  hasstarted,  no  other  process  can  access  the  semaphore  until  the  operation  has  com-pleted or blocked.== %%POSTFIX%%This atomicity is absolutely es*
>%%LINK%%[[#^hu7t11we8k|show annotation]]
>%%COMMENT%%
>
>%%TAGS%%
>
^hu7t11we8k


>%%
>```annotation-json
>{"created":"2024-02-23T07:51:12.828Z","text":"Concurrency issues tend to arise from the interruption of one process to perform another. Since atomic actions means that there are no interruption, there wouldn't be any concurrency issues either.","updated":"2024-02-23T07:51:12.828Z","document":{"title":"MODERN OPERATING SYSTEMS, 5e","link":[{"href":"urn:x-pdf:d2fc41488974e845ac0370313ae095aa"},{"href":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf"}],"documentFingerprint":"d2fc41488974e845ac0370313ae095aa"},"uri":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf","target":[{"source":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf","selector":[{"type":"TextPositionSelector","start":397812,"end":397914},{"type":"TextQuoteSelector","exact":"This atomicity is absolutely essential to solving synchronizationproblems and avoiding race conditions","prefix":"on  has  com-pleted or blocked. ","suffix":". Atomic actions, in which a gro"}]}]}
>```
>%%
>*%%PREFIX%%on  has  com-pleted or blocked.%%HIGHLIGHT%% ==This atomicity is absolutely essential to solving synchronizationproblems and avoiding race conditions== %%POSTFIX%%. Atomic actions, in which a gro*
>%%LINK%%[[#^ii3gkv6tz5|show annotation]]
>%%COMMENT%%
>Concurrency issues tend to arise from the interruption of one process to perform another. Since atomic actions means that there are no interruption, there wouldn't be any concurrency issues either.
>%%TAGS%%
> #os , #concurrency , #COMP3231
^ii3gkv6tz5


>%%
>```annotation-json
>{"created":"2024-02-23T23:28:25.817Z","text":"Definition for a [[process]].","updated":"2024-02-23T23:28:25.817Z","document":{"title":"MODERN OPERATING SYSTEMS, 5e","link":[{"href":"urn:x-pdf:d2fc41488974e845ac0370313ae095aa"},{"href":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf"}],"documentFingerprint":"d2fc41488974e845ac0370313ae095aa"},"uri":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf","target":[{"source":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf","selector":[{"type":"TextPositionSelector","start":278325,"end":278468},{"type":"TextQuoteSelector","exact":"A process is just an instance of an executing program, includ-ing  the  current  values  of  the  program  counter, registers,  and  variables.","prefix":"es, or justprocesses for short. ","suffix":"  Con-ceptually, each  process  "}]}]}
>```
>%%
>*%%PREFIX%%es, or justprocesses for short.%%HIGHLIGHT%% ==A process is just an instance of an executing program, includ-ing  the  current  values  of  the  program  counter, registers,  and  variables.== %%POSTFIX%%Con-ceptually, each  process*
>%%LINK%%[[#^wjzbzqjcwmd|show annotation]]
>%%COMMENT%%
>Definition for a [[process]].
>%%TAGS%%
>
^wjzbzqjcwmd
