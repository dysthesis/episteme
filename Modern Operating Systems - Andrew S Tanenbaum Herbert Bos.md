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


>%%
>```annotation-json
>{"created":"2024-02-24T03:14:07.044Z","text":"The problem with [[Semaphores|semaphores]] that [[Monitors|monitors]] supposedly solve.","updated":"2024-02-24T03:14:07.044Z","document":{"title":"MODERN OPERATING SYSTEMS, 5e","link":[{"href":"urn:x-pdf:d2fc41488974e845ac0370313ae095aa"},{"href":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf"}],"documentFingerprint":"d2fc41488974e845ac0370313ae095aa"},"uri":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf","target":[{"source":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf","selector":[{"type":"TextPositionSelector","start":424562,"end":424898},{"type":"TextQuoteSelector","exact":"This problem is pointed out to show how careful you must be when using sem-aphores.  One  subtle  error  and  everything  comes  to  a  grinding  halt. It  is  like pro-gramming  in  assembly  language,  only  worse,  because  the  errors  are  race  condi-tions, deadlocks, and other forms of unpredictable and irreproducible behavior.","prefix":" deadlocks in detail in Chap. 6.","suffix":"To  make it easier to write corr"}]}]}
>```
>%%
>*%%PREFIX%%deadlocks in detail in Chap. 6.%%HIGHLIGHT%% ==This problem is pointed out to show how careful you must be when using sem-aphores.  One  subtle  error  and  everything  comes  to  a  grinding  halt. It  is  like pro-gramming  in  assembly  language,  only  worse,  because  the  errors  are  race  condi-tions, deadlocks, and other forms of unpredictable and irreproducible behavior.== %%POSTFIX%%To  make it easier to write corr*
>%%LINK%%[[#^vfed0yk0ls|show annotation]]
>%%COMMENT%%
>The problem with [[Semaphores|semaphores]] that [[Monitors|monitors]] supposedly solve.
>%%TAGS%%
>#os, #concurrency, #COMP3231
^vfed0yk0ls


>%%
>```annotation-json
>{"created":"2024-02-24T03:18:04.075Z","text":"Seems like a queue, where some $n$ slots are available in the counter to serve people concurrently. When someone is done and leaves, they execute an `up` to indicate that the next person can be served. At least, that's my understanding of it. [[Binary semaphores]] would have $n=1$, whereas [[Counting semaphores|counting semaphores]] would have $n\\in\\mathbb Z^+$","updated":"2024-02-24T03:18:04.075Z","document":{"title":"MODERN OPERATING SYSTEMS, 5e","link":[{"href":"urn:x-pdf:d2fc41488974e845ac0370313ae095aa"},{"href":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf"}],"documentFingerprint":"d2fc41488974e845ac0370313ae095aa"},"uri":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf","target":[{"source":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf","selector":[{"type":"TextPositionSelector","start":398112,"end":398560},{"type":"TextQuoteSelector","exact":"The up operation increments the value of the semaphore addressed. If one (ormore)  processes  were  sleeping  on  that  semaphore,  unable  to  complete  an  earlierdown operation,  one  of  them  is  chosen  by  the  system  (e.g.,  at  random)  and  is  al-lowed to complete its down. After an up on a semaphore with processes sleepingon it, the semaphore will still have the value of 0. However,  there will be one few-er process sleeping on it.","prefix":"eas of computer science as well.","suffix":" The operation of incrementing t"}]}]}
>```
>%%
>*%%PREFIX%%eas of computer science as well.%%HIGHLIGHT%% ==The up operation increments the value of the semaphore addressed. If one (ormore)  processes  were  sleeping  on  that  semaphore,  unable  to  complete  an  earlierdown operation,  one  of  them  is  chosen  by  the  system  (e.g.,  at  random)  and  is  al-lowed to complete its down. After an up on a semaphore with processes sleepingon it, the semaphore will still have the value of 0. However,  there will be one few-er process sleeping on it.== %%POSTFIX%%The operation of incrementing t*
>%%LINK%%[[#^u5kn66atfz7|show annotation]]
>%%COMMENT%%
>Seems like a queue, where some $n$ slots are available in the counter to serve people concurrently. When someone is done and leaves, they execute an `up` to indicate that the next person can be served. At least, that's my understanding of it. [[Binary semaphores]] would have $n=1$, whereas [[Counting semaphores|counting semaphores]] would have $n\in\mathbb Z^+$
>%%TAGS%%
>#os, #concurrency, #COMP3231
^u5kn66atfz7


>%%
>```annotation-json
>{"created":"2024-02-24T03:32:24.159Z","text":"[[Semaphores]] are used not only to enforce [[Mutual exclusion|mutual exclusion]], but also as a means for synchronisation, ensuring that \"certain sequences of events do not occur.\"","updated":"2024-02-24T03:32:24.159Z","document":{"title":"MODERN OPERATING SYSTEMS, 5e","link":[{"href":"urn:x-pdf:d2fc41488974e845ac0370313ae095aa"},{"href":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf"}],"documentFingerprint":"d2fc41488974e845ac0370313ae095aa"},"uri":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf","target":[{"source":"vault:/Resources/Textbooks/COMP3231/Modern Operating Systems.pdf","selector":[{"type":"TextPositionSelector","start":403081,"end":403865},{"type":"TextQuoteSelector","exact":"In the example of Fig. 2-28, we have actually used semaphores in two differentways. This difference is important enough to make explicit. The mutex semaphoreis used for mutual exclusion. It is designed to guarantee that only one process at atime will be reading or writing the buffer and the associated variables. This mutualexclusion is required to prevent chaos. We will study mutual exclusion and how toachieve it in the next section.The other use of semaphores is for synchronization. The full and empty sem-aphores are needed to guarantee that certain event sequences do or do not occur. Inthis  case,  they ensure  that  the  producer  stops  running  when  the  buffer  is  full,  andthat the consumer stops running when it is empty. This use is different from mutualexclusion.","prefix":"duling later on in this chapter.","suffix":"The Readers and Writers ProblemT"}]}]}
>```
>%%
>*%%PREFIX%%duling later on in this chapter.%%HIGHLIGHT%% ==In the example of Fig. 2-28, we have actually used semaphores in two differentways. This difference is important enough to make explicit. The mutex semaphoreis used for mutual exclusion. It is designed to guarantee that only one process at atime will be reading or writing the buffer and the associated variables. This mutualexclusion is required to prevent chaos. We will study mutual exclusion and how toachieve it in the next section.The other use of semaphores is for synchronization. The full and empty sem-aphores are needed to guarantee that certain event sequences do or do not occur. Inthis  case,  they ensure  that  the  producer  stops  running  when  the  buffer  is  full,  andthat the consumer stops running when it is empty. This use is different from mutualexclusion.== %%POSTFIX%%The Readers and Writers ProblemT*
>%%LINK%%[[#^pbbhz2wxokm|show annotation]]
>%%COMMENT%%
>[[Semaphores]] are used not only to enforce [[Mutual exclusion|mutual exclusion]], but also as a means for synchronisation, ensuring that "certain sequences of events do not occur."
>%%TAGS%%
>#os, #concurrency, #COMP3231
^pbbhz2wxokm
