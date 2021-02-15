---
title: Настройка партнерских приложений в Skype для бизнеса Server 2015 и Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: Сводка. Настройка проверки подлинности "сервер-сервер" для Exchange Server 2016 или Exchange Server 2013 и Skype для бизнеса Server.
ms.openlocfilehash: a707836a43965f477dc037f71bb68cbda8c8e96c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834049"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Настройка партнерских приложений в Skype для бизнеса Server и Exchange Server
 
**Сводка:** Настройка проверки подлинности "сервер-сервер" для Exchange Server 2016 или Exchange Server 2013 и Skype для бизнеса Server.
  
Для проверки подлинности "сервер-сервер" обычно требуются два сервера, которые должны взаимодействовать друг с другом, и сторонний сервер маркеров безопасности. Если серверу A и серверу B необходимо взаимодействовать, оба этих сервера обычно начинают работу с связи с сервером маркеров и получения взаимно доверенного маркера безопасности. Затем сервер А представляет этот маркер безопасности серверу B (и наоборот) как способ гарантировать его подлинность и надежность.
  
Однако это общее правило. Skype для бизнеса Server, Exchange Server 2016, Exchange Server 2013 и SharePoint Server 2013 не требуется использовать сторонний сервер маркеров при связи друг с другом; это потому, что эти серверные продукты могут создавать маркеры безопасности, которые могут быть приняты друг другом без необходимости в отдельном сервере маркеров. (Эта возможность доступна только в Skype для бизнеса Server, Exchange Server 2016, Exchange Server 2013 и SharePoint Server 2013. Для настройки проверки подлинности "сервер-сервер" с другими серверами, включая серверные продукты Майкрософт, потребуется использование стороннего сервера маркеров.
  
Чтобы настроить проверку подлинности "сервер-сервер" между Skype для бизнеса Server и Exchange Server необходимо сделать два действия: 1) необходимо назначить соответствующие сертификаты каждому серверу; и 2) необходимо настроить каждый сервер в качестве партнерского приложения другого сервера: это означает, что Skype для бизнеса Server должен быть партнерским приложением для Exchange Server, а Exchange Server — партнерским приложением для Skype для бизнеса Server.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Настройка Skype для бизнеса Server в качестве партнерского приложения для Exchange Server

Самый простой способ настроить Skype для бизнеса Server в качестве партнерского приложения с Exchange Server 2016 или Exchange Server 2013 — запустить сценарий Configure-EnterprisePartnerApplication.ps1, который Windows PowerShell вместе с Exchange Server. Чтобы запустить этот сценарий, необходимо предоставить URL-адрес для документа метаданных проверки подлинности Skype для бизнеса Server; Обычно это полное доменное имя пула Skype для бизнеса Server, за которым следует суффикс /metadata/json/1. Пример:
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Чтобы настроить Skype для бизнеса Server в качестве партнерского приложения, откройте командную оболочку Exchange и запустите команду, аналогичную этой (предполагается, что Exchange установлен на диске C: и использует путь к папке по умолчанию):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

После настройки партнерского приложения рекомендуется остановить и перезапустить службы IIS на серверах почтовых ящиков и клиентского доступа Exchange. Для перезапуска служб IIS можно использовать команду, аналогичную указанной, которая выполнит перезапуск службы на компьютере atl-exchange-001:
  
```powershell
iisreset atl-exchange-001
```

Эту команду можно выполнить в командной оболочке Exchange или в любом другом командном окне с привилегиями администратора.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Настройка Exchange Server в качестве партнерского приложения для Skype для бизнеса Server

После настройки Skype для бизнеса Server в качестве партнерского приложения для Exchange Server 2016 или Exchange Server 2013 необходимо настроить Exchange Server в качестве партнерского приложения для Skype для бизнеса Server. Это можно сделать с помощью оболочки управления Skype для бизнеса Server и указания документа метаданных проверки подлинности для Exchange; Обычно это URI службы автообнаружия Exchange, за которым следует суффикс /metadata/json/1. Пример:
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

В Skype для бизнеса Server партнерские приложения настраиваются с помощью [cmdlet New-CsPartnerApplication.](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) Помимо указания URI метаданных необходимо также задать для уровня доверия приложения полное; Это позволит Exchange представлять как самого себя, так и любого авторизованного пользователя в области. Пример:
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Кроме того, можно создать партнерского приложения путем копирования и изменения кода скрипта, найденного в документации по проверке подлинности "сервер-сервер" Skype для бизнеса Server. Дополнительные сведения см. в статье "Управление проверкой подлинности между серверами [(OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) и партнерскими приложениями в Skype для бизнеса Server".
  
Если вы успешно настроили партнерские приложения для Skype для бизнеса Server и Exchange Server, вы также успешно настроили проверку подлинности "сервер-сервер" между двумя продуктами. Skype для бизнеса Server включает в себя Windows PowerShell [Test-CsExStorageConnectivity,](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) который позволяет проверить правильность настройки проверки подлинности "сервер-сервер" и возможность подключения службы хранилища Skype для бизнеса Server к Exchange Server. Для этого он подключается к почтовому ящику пользователя Exchange Server, записи элемента в папку "История бесед" для этого пользователя, а затем (при желании) удаляет этот элемент.
  
Чтобы проверить интеграцию Skype для бизнеса Server и Exchange Server, в командной оболочке Skype для бизнеса Server запустите следующую команду:
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

В предыдущей команде SipUri представляет SIP-адрес пользователя с учетной записью на Exchange Server; Команда не будет работать, если это не действительная учетная запись пользователя.
  
> [!NOTE]
> Если вы получили ответ 401 от этого cmdlet, вероятно, это происходит потому, что конфигурация по умолчанию для Exchange не включает поддержку принятие маркеров Oauth. Дополнительные сведения об использовании Oauth в Exchange см. в подстроке "Настройка проверки подлинности [OAuth в SharePoint 2013 и Skype для бизнеса Server".](https://go.microsoft.com/fwlink/p/?LinkId=513103) 
  
Если проверка завершилась успешно и соединение было установлено, можно перейти к настройке дополнительных компонентов, таких как интеграция службы архивации и единое хранилище контактов.
