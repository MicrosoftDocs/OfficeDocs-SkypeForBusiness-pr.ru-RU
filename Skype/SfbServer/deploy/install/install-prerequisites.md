---
title: Установка обязательных компонентов для Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Summary: Learn about the servers and server roles you must configure before you install Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 6f84b4f0a95c45297ad809e6b04217e711c3dd5e
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a>Установка обязательных компонентов для Skype для бизнеса Server 2015
 
**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015. Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
При настройке Windows Server на каждом из серверов в топологии устанавливаются роли и функции, которые являются необходимыми компонентами. Требования зависят от роли, которую выполняет сервер в топологии. Шаги 1–5 можно выполнять в любом порядке. Однако шаги 6, 7 и 8 необходимо выполнять в указанном порядке и только после шагов 1–5, как показано на схеме. Обязательные компоненты устанавливаются на шаге 1 из 8.
  
![Обзорная схема - установка предварительных компонентов.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a>Настройка Windows Server

Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed. For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  
> [!TIP]
> Здесь приведена процедура для Windows Server 2012 R2. Процедуры для других версий Windows Server могут незначительно отличаться. 
  
> [!IMPORTANT]
> Before you begin, make sure that Windows Server is up-to-date by using Windows Update. 
  
![Windows Server обновлен.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
Посмотрите видео с инструкциями по **установке необходимых компонентов**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a>Установка необходимых ролей и компонентов для серверов переднего плана

1. Откройте диспетчер серверов и щелкните **Добавить роли и компоненты**.
    
2. Прочитайте страницу **Перед началом работы** для ознакомления с процедурой установки ролей и компонентов в Windows Server, затем нажмите кнопку **Далее**.
    
3. Выберите **Установка ролей или компонентов** и нажмите кнопку **Далее**.
    
4. Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.
    
5. Выберите роль **Web Server (IIS)** и при появлении всплывающего окна с обязательными компонентами щелкните **Добавить компоненты**, затем нажмите кнопку **Далее**.
    
6. Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015. Here's an abbreviated list:
    
   - .NET Framework Features
    
   - Службы WCF
    
   - Активация HTTP
    
    > [!NOTE]
    > Для активации HTTP необходимы дополнительные компоненты. Щелкните **Добавить компоненты** в диалоговом окне предупреждения, всплывающем при выборе активации HTTP.
  
   - Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)
    
   - Средства удаленного администрирования сервера
    
   - Средства администрирования ролей
    
   - AD DS 
    
   - AD LDS
    
   - Windows Identity Foundation 3.5
    
7. Для продолжения работы с мастером нажмите кнопку **Далее**.
    
8. Прочитайте заметки о **роли веб-сервера (IIS)**, затем нажмите кнопку **Далее**.
    
9. Выберите следующие **службы роли веб-сервера (IIS)**.
    
   - Основные возможности HTTP
    
   - Документ по умолчанию
    
   - Просмотр каталога
    
   - Ошибки HTTP
    
   - Статическое содержимое
    
   - Работоспособность и диагностика
    
   - Ведение журнала HTTP
    
   - Средства ведения журналов
    
   - Трассировка
    
   - Производительность
    
   - Сжатие статического содержимого
    
   - Сжатие динамического содержимого
    
   - Безопасность
    
   - Фильтрация запросов
    
   - Проверка подлинности с сопоставлением сертификатов клиентов
    
   - Проверка подлинности Windows
    
   - Разработка приложений
    
   - .NET Extensibility 3.5
    
   - .NET Extensibility 4.5
    
   - ASP.NET 3.5
    
   - ASP.NET 4.5
    
   - Расширения ISAPI
    
   - Фильтры ISAPI
    
   - Средства управления
    
   - Консоль управления IIS
    
   - Сценарии и средства управления для служб IIS
    
10. Для продолжения работы с мастером нажмите кнопку **Далее**.
    
11. Проверьте выбор компонентов установки, и убедитесь в том, что все обязательные компоненты выбраны, затем нажмите кнопку **Установить**.
    
    > [!CAUTION]
    > По умолчанию в Windows Server 2012 R2 не устанавливаются все исходные файлы для обязательных компонентов. Если сервер не подключен в сети Интернет, для установки обязательных компонентов потребуется установить носитель Windows Server 2012 R2 и выбрать **Указать альтернативный исходный путь**. Исходные файлы находятся в каталоге sources\sxs. Например, если носитель Windows Server 2012 R2 установлен в дисковод D, следует указать путь `d:\sources\sxs`. > It is important that you have the latest updates from Windows Update. При отсутствии интернет-подключения потребуется вручную установить все необходимые пакеты обновления, а также обязательные компоненты для этих пакетов. 
  
12. Когда в диалоговом окне появляется сообщение о завершении установки, для окончательного завершения процесса необходимо перезагрузить сервер.
    
13. Снова запустите **центр обновления Windows** и проверьте наличие обновлений для установленных ролей и служб.
    
14. If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight. To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).
    
Обязательные компоненты можно установить с помощью следующей команды PowerShell. Следует учитывать, что при выполнении этой команды поиск исходных файлов осуществляется в определенном порядке. При наличии интернет-подключения команда обращается к центру обновления Windows. Однако в автономном режиме необходимо обеспечить доступность исходных файлов для команды. For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx). Даже в случае установки обязательных компонентов с помощью команды PowerShell не забудьте по завершении установки снова запустить центр обновления Windows.
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> Для серверов, роль которых отличается от роли сервера переднего плана, например для директоров, серверов сохраняемого чата и пограничных серверов, предусмотрены особые наборы обязательных компонентов. For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  

