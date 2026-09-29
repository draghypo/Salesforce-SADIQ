                            Why Salesforce has introduced govenor limits in salesforce
                        --------------------------------------------------------------------
**Salesforce follow the multi tenat archtecture: -** Multi-tenant means multiple companies share the exact same underlying technology, software servers, and database hardware, while keeping their data completely private and isolated.

  
**Reason: -** Salesforce introduced Governor Limits to protect its multi-tenant architecture. Since many companies share the same cloud
servers and database, bad code from one company could slow down or crash the system for everyone else—this is called 
the 'noisy neighbor' effect. Governor Limits set strict rules on resources like CPU time, memory, and database queries 
so no single company can hog the server.

  In simple Hinglish some points : - 
  * **Shared Storage (Hyperforce / AWS):** Infosys, TCS, aur Accenture—teeno ka data Hyperforce (AWS) ke andar ek hi shared database engine par hota hai.
  * **Data Isolation (Org_Id):** Database level par Org_Id ki waja se Infosys ko sirf Infosys ka record dikhta hai, TCS ko sirf TCS ka, aur Accenture ko sirf Accenture ka.
  * **Noisy Neighbor Problem:** Agar Infosys ka developer bina Governor Limits ke ek aisa Apex code likh de jo infinite loop mein SOQL chalaaye ya Heap memory full kar de, toh AWS server ka CPU/RAM 100% consume ho jayega.
  * **Impact on Others:** Isse TCS aur Accenture ke users ka Salesforce bhi slow ho jayega ya hang hone lagega.
  * **Governor Limits (The Traffic Cop):** Isi issue ko rokne ke liye Salesforce Governor Limits laya. Jaise hi Infosys ka code limit exceed karega (jaise 101st query ya 6MB heap limit), Salesforce us single transaction ko turant kill kar dega (LimitException fek kar)—taaki TCS aur Accenture ko pata bhi na chale aur unka system bina kisi lag ke chalta rahe.
