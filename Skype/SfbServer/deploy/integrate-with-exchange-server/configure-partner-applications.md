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
description: Сводка. Настройка проверки подлинности сервера для Exchange Server 2016 или Exchange Server 2013 г. и Skype для бизнеса Server.
ms.openlocfilehash: 47f192ce11a48ab4c256ac6a1f499aa24563a725
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110115"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Настройка партнерских приложений в Skype для бизнеса Server и Exchange Server
 
**Сводка:** Настройка проверки подлинности сервера для Exchange Server 2016 или Exchange Server 2013 г. и Skype для бизнеса Server.
  
Для проверки подлинности от сервера к серверу обычно требуется два сервера, которые должны взаимодействовать друг с другом, и сторонний сервер маркеров безопасности. Если серверу A и серверу B требуется связь, то оба этих сервера обычно начинаются с контакта с сервером маркеров и получения взаимно доверенного маркера безопасности. Сервер A затем представляет этот маркер безопасности серверу B (и наоборот) как способ гарантировать его подлинность и надежность.
  
Однако это общее правило. Skype для бизнеса Server, Exchange Server 2016, Exchange Server 2013 и SharePoint Server 2013, не нужно использовать сторонний сервер маркеров при общении друг с другом; Это потому, что эти серверные продукты могут создавать маркеры безопасности, которые могут быть приняты друг другом без необходимости отдельного сервера маркеров. (Эта возможность доступна только в Skype для бизнеса Server, Exchange Server 2016, Exchange Server 2013 и SharePoint Server 2013. Для настройки проверки подлинности "сервер-сервер" с другими серверами, включая серверные продукты Майкрософт, потребуется использование стороннего сервера маркеров.
  
Чтобы настроить проверку подлинности от сервера к серверу между Skype для бизнеса Server и Exchange Server необходимо сделать две вещи: 1) необходимо назначить соответствующие сертификаты на каждый сервер; и 2) необходимо настроить каждый сервер как партнерского приложения другого сервера: это означает, что вы должны настроить Skype для бизнеса Server, чтобы быть партнером приложения для Exchange Server, и вы должны настроить Exchange Server, чтобы быть партнером приложения для Skype для бизнеса Server.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Настройка Skype для бизнеса Server для партнерского приложения для Exchange Server

Самый простой способ настройки Skype для бизнес-сервера в качестве партнерского приложения с Exchange Server 2016 или Exchange Server 2013 г. — это запустить сценарий Configure-EnterprisePartnerApplication.ps1— сценарий Windows PowerShell, который Exchange Server. Чтобы запустить этот сценарий, необходимо предоставить URL-адрес для документа метаданных проверки подлинности Skype для бизнеса Server; обычно это будет полностью квалифицированное доменное имя пула Skype для бизнеса Server, за которым следует суффикс/метаданные/json/1. Например:
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Чтобы настроить Skype для бизнеса Server в качестве партнерского приложения, откройте командную оболочку Exchange и запустите команду, аналогичную этой (если предположить, что Exchange установлена на диске C: и что она использует путь папки по умолчанию):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

После настройки партнерского приложения рекомендуется остановить и перезапустить службы интернет-информации (IIS) на почтовом ящике Exchange и серверах клиентского доступа. Для перезапуска служб IIS можно использовать команду, аналогичную указанной, которая выполнит перезапуск службы на компьютере atl-exchange-001:
  
```powershell
iisreset atl-exchange-001
```

Эта команда может запускаться из командной оболочки Exchange или из любого другого окна команды, запускаемого в соответствии с привилегиями администратора.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Настройка Exchange Server партнерского приложения для Skype для бизнеса Server

После настройки Skype для бизнес-сервера в качестве партнерского приложения для Exchange Server 2016 или Exchange Server 2013 года необходимо настроить Exchange Server для партнерского приложения для Skype для бизнеса Server. Это можно сделать с помощью оболочки управления Skype для бизнес-серверов и указания документа метаданных проверки подлинности для Exchange; обычно это будет URI службы автообнаружия Exchange, за которой следует суффикс/метаданные/json/1. Например:
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

В Skype для бизнеса Server партнерские приложения настраиваются с помощью комлета [New-CsPartnerApplication.](/powershell/module/skype/new-cspartnerapplication?view=skype-ps) Помимо указания URI метаданных необходимо также задать уровень доверия приложения к Full; это позволит Exchange представлять как себя, так и любого уполномоченного пользователя в области. Например:
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Кроме того, можно создать партнерского приложения, копируя и изменяя код скрипта, найденный в документации по проверке подлинности сервера на сервере Skype для бизнеса. Дополнительные сведения см. в статье Управление проверкой подлинности от сервера к серверу [(OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) и партнерскими приложениями в статье Skype для бизнеса Server.
  
Если вы успешно настроили партнерские приложения как для Skype для бизнес-сервера, так и для Exchange Server, вы также успешно настроили проверку подлинности от сервера к серверу между двумя продуктами. Skype для бизнеса Server включает в себя [Windows PowerShell,Test-CsExStorageConnectivity,](/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) который позволяет проверить правильность проверки подлинности на сервере и подключение службы хранения данных Skype для бизнеса к Exchange Server. Это делается, подключившись к почтовому ящику пользователя Exchange Server, написав элемент в папку История бесед для этого пользователя, а затем (необязательно) удалив этот элемент.
  
Чтобы проверить интеграцию Skype для бизнеса Server и Exchange Server, запустите команду, аналогичную следующей из командной оболочки Skype для бизнеса Server:
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

В предыдущей команде SipUri представляет SIP-адрес пользователя с учетной записью на Exchange Server; Ваша команда не будет работать в этом случае не является допустимой учетной записью пользователя.
  
> [!NOTE]
> Если вы получите ответ 401 из этого комлета, это, вероятно, потому, что конфигурация по умолчанию для Exchange не включает поддержку для приемки маркеров Oauth. Дополнительные сведения об использовании Oauth в Exchange см. в раздел Настройка проверки подлинности [OAuth в SharePoint 2013](/exchange/configure-oauth-authentication-with-sharepoint-2013-and-lync-2013-exchange-2013-help)и Skype для бизнеса Server. 
  
Если проверка завершилась успешно и соединение было установлено, можно перейти к настройке дополнительных компонентов, таких как интеграция службы архивации и единое хранилище контактов.