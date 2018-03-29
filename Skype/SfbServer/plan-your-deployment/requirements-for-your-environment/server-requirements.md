---
title: Требования к серверу для Skype для бизнеса Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 'Summary: Prepare your Skype for Business Server 2015 servers with this topic. Представленная здесь информация об оборудовании, ОС, базах данных, программном обеспечении, а также все системные требования и рекомендации помогут выполнить установку и развертывание фермы серверов.'
ms.openlocfilehash: 8a86c96554d7aa1be0597c5c82614cd43816540f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Требования к серверу для Skype для бизнеса Server 2015
 
**Краткое содержание.** В данном разделе описывается подготовка серверов Skype для бизнеса Server 2015. Представленная здесь информация об оборудовании, ОС, базах данных, программном обеспечении, а также все системные требования и рекомендации помогут выполнить установку и развертывание фермы серверов.
  
As you might expect, there are some preparations to make before you begin deploying Skype for Business Server 2015. This article will walk you through planning for the following:
  
- [Оборудование для Skype для бизнеса Server 2015](server-requirements.md#Hardware)
  
- [Operating systems for Skype for Business Server 2015](server-requirements.md#OS)
  
- [Внутренние базы данных, которые будут работать с Skype для бизнеса Server 2015](server-requirements.md#DBs)
  
- [Программное обеспечение, которое следует установить перед развертыванием Skype для бизнеса Server 2015](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Оборудование для Skype для бизнеса Server 2015
<a name="Hardware"> </a>

Now that you have your topology down (and if you don't, you can check out the [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) topic), it's time to think about servers. Skype for Business Server 2015 servers will require 64-bit hardware. Ниже приведены рекомендации по оборудованию. These aren't requirements, but they reflect the requirements necessary for optimal performance. Документация по планированию загрузки позволяет определить, не требуется ли более мощное оборудование с учетом конкретных обстоятельств.
  
Recommended hardware for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers:
  
|**Hardware component**|**Recommended**|
|:-----|:-----|
|ЦП  <br/> |Два 64-разрядных шестиядерных процессора с частотой 2,26 ГГц или выше.  <br/> Intel Itanium processors are not supported for Skype for Business Server 2015 roles.  <br/> |
|Память  <br/> |32 ГБ.  <br/> |
|Диск  <br/> |ЛЮБОЙ ИЗ ВАРИАНТОВ:  <br/> • 8 и больше жестких дисков с 10 000 об/мин и не менее 72 ГБ свободного места на диске (два диска объединены в RAID 1, а 6 — в RAID 10).   <br/> ИЛИ  <br/> • твердотельные накопители, которые способны обеспечить свободное пространство и производительность, соответствующие 8 механическим жестким дискам с 10 000 об/мин.  <br/> |
|Сеть  <br/> |1 двухпортовый сетевой адаптер, 1 Гбит/с или выше (можно использовать 2 сетевых адаптера, но их необходимо объединить с одним MAC-адресом и одним IP-адресом).  <br/> Dual or multi-homed configurations are **not** supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers. <br/> Поскольку они не предоставляются операционной системе и используются для мониторинга оборудования сервера и управления им, вы можете использовать системы внешнего управления, такие как DRAC или ILO. Этот сценарий не предполагает использования многоадресного сервера и поддерживается.<br/> |
   
Recommended hardware for Edge Servers, standalone Mediation Servers, Video Interop Servers, and Directors:
  
|**Hardware component**|**Recommended**|
|:-----|:-----|
|ЦП  <br/> |64-разрядный процессор с двухканальным кэшем, четырехъядерный, 2,26 ГГц и выше.  <br/> Intel Itanium processors are not supported for Skype for Business Server 2015 roles.  <br/> |
|Память  <br/> |16 гигабайт.  <br/> |
|Диск  <br/> |ЛЮБОЙ ИЗ ВАРИАНТОВ:  <br/> • 4 и больше жестких дисков с 10 000 об/мин и не менее 72 ГБ свободного места на диске (диски должны быть объединены в конфигурацию 2x RAID 1).  <br/> ИЛИ  <br/> • твердотельные накопители, которые способны обеспечить свободное пространство и производительность, соответствующие 4 механическим жестким дискам с 10 000 об/мин.  <br/> |
|Сеть  <br/> |1 двухпортовый сетевой адаптер, 1 Гбит/с или выше (можно использовать 2 сетевых адаптера, но их необходимо объединить с одним MAC-адресом и одним IP-адресом).  <br/> Dual or multi-homed configurations are **not** supported for Video Interop Servers and Directors. <br/> Пограничным серверам потребуется два сетевых интерфейса — двухпортовые сетевые адаптеры со скоростью передачи 1 Гбит/с или выше (или два сопряженных сетевых адаптера (всего четыре), каждая пара объединена с одним MAC-адресом и одним IP-адресом, всего две пары).  <br/> On standalone Mediation Servers the installation of additional network interface cards (NICs) to allow the configuration of a specific PSTN IP address is supported.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Operating systems for Skype for Business Server 2015
<a name="OS"> </a>

Once you have the hardware in place, you'll need to install operating systems (OS). These are the OS that will allow you to install and successfully use Skype for Business Server 2015.
  
|||
|:-----|:-----|
|Windows Server 2016  <br/> ||
|Windows Server 2012 R2 Datacenter OS with all required updates installed.  <br/> |Windows Server 2012 R2 Standard OS with all required updates installed.  <br/> |
|Windows Server 2012 Datacenter OS with all required updates installed.  <br/> |Windows Server 2012 Standard OS with all required updates installed.  <br/> |
   
If it's not on this list, it won't work properly, please don't try it for new installs of Skype for Business Server 2015.
  
> [!NOTE]
> Можно было заменить, что Windows Server 2008 R2 нет в этом списке. Это связано с тем, что мы рекомендуем Windows Server 2012 R2 для всех новых серверов, используемых для Skype для бизнеса. Windows Server 2008 R2 следует использовать только в том случае, если есть серверы с уже установленной версией Lync Server 2013 и для них планируется обновление на месте. Основной жизненный цикл поддержки Windows Server 2008 R2 завершился 13.01.2015. 
  
В дополнение к последнему пакету обновления можно проверить установку следующих обновлений (где это уместно):
  
- Перед обновлением Windows Server 2012 необходимо установить исправления из статьи базы знаний 2858668. [Get it here](https://support.microsoft.com/en-us/kb/2858668/).
    
- Если у вас Windows Server 2012 R2, перед его обновлением установите исправления из статьи базы знаний 2982006. [It's found here](https://support.microsoft.com/en-us/kb/2982006/).
    
- If you're upgrading on a Windows Server 2008 R2 box (see the Note above), then you'll want to install KB article 2533623 first. [It's at this link](https://support.microsoft.com/en-us/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Внутренние базы данных, которые будут работать с Skype для бизнеса Server 2015
<a name="DBs"> </a>

When installing Skype for Business Server 2015 Standard Edition, you'll have SQL Server 2014 Express (64-bit edition) is automatically installed as well.
  
Skype for Business Server 2015 Enterprise Edition is a little more complicated, but the supported list is below (everything is 64-bit edition, you'll notice, please don't use 32-bit editions):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2014 Enterprise (64-bit edition), and you must run with Cumulative Update 6 or later ([download Cumulative Update 6](https://support.microsoft.com/en-us/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (64-bit edition), and we recommend running with the latest service pack.  <br/> |Microsoft SQL Server 2008 R2 Enterprise (64-bit edition), and we recommend running with the latest service pack.  <br/> |
|Microsoft SQL Server 2014 Standard (64-bit edition), and you must run with Cumulative Update 6 or later ([download Cumulative Update 6](https://support.microsoft.com/en-us/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Standard (64-bit edition), and we recommend running with the latest service pack.  <br/> |Microsoft SQL Server 2008 R2 Standard (64-bit edition), and we recommend running with the latest service pack  <br/> |
   
If you don't see the SQL Server edition you want to use listed here, you can't use it.
  
> [!NOTE]
> You're also going to need to install SQL Server Reporting Services for the Monitoring Server role, but we need you to know this isn't going to be supported with SQL Always on until post-RTM. 
  
### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>Зеркальное отображение SQL, кластеризация SQL и SQL Always On

You are able to use SQL Mirroring or SQL Clustering with Skype for Business Server 2015, it's supported. SQL Mirroring's set up through the Skype for Business Server Topology Builder. If you're intent on setting up SQL Clustering, that's done in SQL Server.
  
Make sure you have an active/passive configuration for SQL Clustering, as that's what's supported. Don't share the passive node with any other SQL instance.
  
Для отказоустойчивой кластеризации требуется следующее.
  
Два узла:
  
- Microsoft SQL Server 2014 Standard (64-bit edition), and we recommend running with the latest service pack.
    
-  Microsoft SQL Server 2012 Standard (64-bit edition), and we recommend running with the latest service pack.
    
- Microsoft SQL Server 2008 R2 Standard (64-bit edition), and we recommend running with the latest service pack.
    
16 узлов:
  
- Microsoft SQL Server 2014 Enterprise (64-bit edition), and we recommend running with the latest service pack.
    
- Microsoft SQL Server 2012 Enterprise (64-bit edition), and we recommend running with the latest service pack.
    
- Microsoft SQL Server 2008 R2 Enterprise (64-bit edition), and we recommend running with the latest service pack.
    
> [!IMPORTANT]
> For upgrading, we do want you to ensure that on your Front End Servers you have at least SQL Server 2012 SP1 installed prior to upgrade. [Here's a link](https://www.microsoft.com/en-us/download/details.aspx?id=35575) to SP1 if you want to download it right away.
  
If you need to read up more on SQL Mirroring, we have a Back End Server high availability in Skype for Business Server 2015 topic. Configure SQL Server clustering for Skype for Business Server 2015 has the steps for getting clustering ready. There are also further links on failover clustering for SQL, for [2014](https://technet.microsoft.com/en-us/library/hh231721.aspx), [2012](https://technet.microsoft.com/en-us/library/hh231721%28v=sql.110%29.aspx), and [2008](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> Поддержка SQL Always On — новая возможность в этом выпуске. It is supported, and you can read more about it in the [Back End Server high availability in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) topic.
  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Программное обеспечение, которое следует установить перед развертыванием Skype для бизнеса Server 2015
<a name="Software"> </a>

There are some things you're going to need to install or configure for any server running Skype for Business Server 2015, and they're listed below. After that are additional requirements for specific server roles.
  
 **Все серверы:**
  
|**Software/Role**|**Сведения**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |All Skype for Business Server servers need Windows PowerShell 3.0 installed.  <br/> • If you're doing the installation on Windows Server 2012 or Windows Server 2012 R2, you're set, because it's already there.  <br/> • If you're doing an upgrade on Windows Server 2008 R2, you can download the [Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) to get it. <br/> **Tip:** Once you have the correct PowerShell on there, confirm that it's BuildVersion 6.2.9200.0 or later by going to the PowerShell prompt and typing `$PSVersionTable`. Появится нужная вам информация.  <br/> |
|Microsoft .NET Framework  <br/> |WCF services is a **Feature** that's installed as a Windows feature, under **Server Manager**, no downloads needed. <br/> • You need to make sure, when you install this feature, or if it's already installed and you're checking on it, that the **HTTP Activation** option is also checked and installed, like so: <br/> ![Screenshot showing HTTP Activation option under the .NET Framework 4.5 Features.](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)Don't worry if you get an additional pop-up saying some other things need to be installed for HTTP Activation to be installed. That's normal, click OK and go ahead. If you don't get this pop-up, then assume those things are already installed, and go ahead.  <br/> Microsoft .NET Framework is usually installed when Windows Server 2012 R2 or Windows Server 2016 are installed. Skype for Business Server works with the following Microsoft .NET Framework versions:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7 (for Skype for Business Server CU 5 or later releases)  <br/>  .NET Framework 3.5 will likely be installed by default on your Windows Server 2008 R2 machine (definitely check to be sure before you upgrade), but it actually won't be on your Windows Server 2012/Windows Server 2012 R2 servers (for new installations). To add it in, you'll need access to your installation drive or media (the place your Windows Server was installed from, or where the install files are now). Затем продолжите процедуру, установите эту платформу как компонент в диспетчере серверов и укажите путь к установочному носителю (в частности, папку **\sources\sxs**) при появлении соответствующего запроса. <br/> |
|Media Foundation  <br/> |For Windows Server 2016, Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.  <br/> All Front End Servers and Standard Edition servers used for conferencing require Windows Media Format Runtime to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.  <br/> |
|Windows Identity Foundation  <br/> |We need Windows Identity Foundation 3.5 to support server-to-server authentication scenarios for Skype for Business Server 2015.  <br/> • For Windows Server 2012 and Windows Server 2012 R2, there's no need to download anything. Откройте **диспетчер серверов** и перейдите к **мастеру добавления ролей и компонентов**. Компонент **Windows Identity Foundation 3.5** перечислен в разделе **Компоненты**. If it's checked, you're good. В противном случае отметьте его и нажмите кнопку "Далее", чтобы перейти к кнопке **Установить**. <br/> |
|Средства удаленного администрирования сервера  <br/> |Средства администрирования ролей: инструменты AD DS и AD LDS  <br/> |
   
 **Front End Servers and Standard Edition server also need:**
  
|**Software/Role**|**Сведения**|
|:-----|:-----|
|Службы IIS  <br/> |IIS is needed on all Front End Servers, as well as all Standard Edition servers, with the following modules selected:  <br/> • Common HTTP Features: Default Document, HTTP Errors, Static Content  <br/> • Health and Diagnostics: HTTP Logging, Logging Tools, Tracing  <br/> • Performance: Static Content Compression, Dynamic Content Compression  <br/> • Security: Request Filtering, Client Certificate Mapping Authentication, Windows Authentication  <br/> • Application Development: .NET Extensibility 3.5, .NET Extensibility 4.5, ASP.NET 3.5, ASP.NET 4.5, ISAPI Extensions, ISAPI Filters  <br/> • Management Tools: IIS Management Console, IIS Management Scripts and Tools  <br/> We should also note Anonymous Access is also needed, but you get that when you install IIS, so you don't have a place to select that on the list.  <br/> |
|Windows Media Format Runtime  <br/> | For Windows Server 2016, Windows Server 2012, and Windows Server 2012 R2, you'll need to install the **Media Foundation** feature in **Server Manager**. Now, you actually can start your Skype for Business Server 2015 installation without this one, but you'll be prompted to install it, and then reboot the server, before the Skype for Business Server 2015 install continues. Лучше сделать это заранее. <br/> |
|Silverlight  <br/> |You can install the latest version of Silverlight at [this link](https://www.microsoft.com/silverlight/).  <br/> |
   
В качестве помощи в установке приведем ниже пример сценария PowerShell для автоматического запуска:
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Directors also need:**
  
IIS, с выбранными следующими модулями:
  
- Основные возможности HTTP
    
  - Документ по умолчанию
    
  - Ошибки HTTP
    
  - Статическое содержимое
    
- Работоспособность и диагностика
    
  - Ведение журнала HTTP
    
  - Средства ведения журналов
    
  - Трассировка
    
- Производительность
    
  - Сжатие статического содержимого
    
- Безопасность
    
  - Фильтрация запросов
    
  - Проверка подлинности с сопоставлением сертификатов клиентов
    
  - Проверка подлинности Windows
    
- Разработка приложений
    
  - .NET Extensibility 3.5
    
  - .NET Extensibility 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - Расширение ISAPI
    
  - Фильтры ISAPI
    
(If you're wondering, it's the same module set as the Front End Servers and Standard Edition servers, with the Dynamic Content Compression and Management Tools left out.)
  
Кроме того, для него приводится фрагмент кода PowerShell ниже:
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Persistent Chat Servers also need:**
  
Очередь сообщений, которая также называется MSMQ. It's a Windows Server component, and you can install it under the Features section in Server Manager. If you want to read more about this, check out [Installing and Managing Message Queuing](https://technet.microsoft.com/en-us/library/cc771474.aspx).
  
 **Последние рекомендации:**
  
Please don't install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software (any third-party firewalls or anti-virus network inspection software would be included here) on any of your front end servers or standalone mediation servers. Poor media traffic performance has been seen when that software's installed.
  

