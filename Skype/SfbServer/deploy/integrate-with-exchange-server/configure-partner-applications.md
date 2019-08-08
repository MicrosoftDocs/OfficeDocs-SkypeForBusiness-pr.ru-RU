---
title: Настройка партнерских приложений в Skype для бизнеса Server 2015 и Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 'Сводка: Настройка проверки подлинности сервера для Exchange Server 2016 или Exchange Server 2013 и Skype для бизнеса Server.'
ms.openlocfilehash: 5a1958db05ea1e4fae37737512368d509b3c62cf
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245513"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Настройка партнерских приложений в Skype для бизнеса Server и Exchange Server
 
**Сводка:** Настройка проверки подлинности сервера для Exchange Server 2016 или Exchange Server 2013 и Skype для бизнеса Server.
  
Для проверки подлинности "сервер-сервер" обычно требуется два сервера, которые должны обмениваться данными, и сторонний сервер маркеров безопасности. Если сервер A и сервер B нуждаются в общении, то оба эти сервера обычно начинают с того, что они поставляются с сервером-маркером и получают взаимно доверенные маркеры безопасности. Затем сервер A отправляет этот маркер безопасности серверу B (и наоборот) в качестве гарантии своей подлинности и надежности.
  
Однако это общее правило. Skype для бизнеса Server, Exchange Server 2016, Exchange Server 2013 и SharePoint Server 2013 не требуется использовать сторонний сервер маркеров при взаимодействии друг с другом. Это может быть вызвано тем, что эти серверные продукты могут создавать маркеры безопасности, которые могут принимать друг друга, без необходимости использования отдельного сервера маркеров. (Эта возможность доступна только в Skype для бизнеса Server, Exchange Server 2016, Exchange Server 2013 и SharePoint Server 2013. Для настройки проверки подлинности "сервер-сервер" с другими серверами, включая серверные продукты Microsoft, потребуется использование стороннего сервера маркеров.)
  
Чтобы настроить серверную проверку подлинности между Skype для бизнеса Server и Exchange Server, необходимо выполнить два действия: 1) необходимо назначить соответствующие сертификаты каждому серверу. и 2) необходимо настроить каждый сервер так, чтобы он был партнерским приложением другого сервера: это означает, что необходимо настроить Skype для бизнеса Server для использования партнера в Exchange Server, а также настроить сервер Exchange для использования в качестве партнерского приложения Skype. для Business Server.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Настройка Skype для бизнеса Server для работы в качестве партнерских приложений для Exchange Server

Самый простой способ настроить Skype для бизнеса Server — это партнерское приложение с Exchange Server 2016 или Exchange Server 2013 — запуск сценария Конфигуре-ентерприсепартнераппликатион. ps1 — сценария Windows PowerShell, который поставляется вместе с Exchange Server. Чтобы выполнить этот сценарий, необходимо указать URL-адрес для документа метаданных проверки подлинности в Skype для бизнеса Server. как правило, это полное доменное имя пула сервера Skype для бизнеса, за которым следует суффикс/Metadata/JSON/1. Например:
  
```
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Чтобы настроить сервер Skype для бизнеса в качестве партнерского приложения, откройте командную консоль Exchange и выполните следующую команду (предполагая, что Exchange установлен на диске C: и используется путь к папке по умолчанию):
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

После настройки приложения-партнера рекомендуется остановить и перезапустить службы IIS в почтовом ящике Exchange и на серверах клиентского доступа. Ниже приведен пример команды перезапуска служб IIS, относящийся к компьютеру atl-exchange-001.
  
```
iisreset atl-exchange-001
```

Эту команду можно выполнить в командной консоли Exchange или в любом другом окне команд, которое запускается с правами администратора.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Настройка сервера Exchange Server в качестве партнерской программы для Skype для бизнеса Server

После того как вы настроили Skype для Business Server как приложение-партнер для Exchange Server 2016 или Exchange Server 2013, необходимо настроить сервер Exchange Server для работы в качестве партнерского приложения для Skype для бизнеса Server. Это можно сделать с помощью командной консоли Skype для бизнеса Server и указав документ метаданных проверки подлинности для Exchange; как правило, это URI службы автообнаружения Exchange, за которой следует суффикс/Metadata/JSON/1. Например:
  
```
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

В Skype для бизнеса Server партнерские приложения настраиваются с помощью командлета [New-кспартнераппликатион](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) . В дополнение к указанию URI метаданных необходимо также установить полный уровень доверия для приложения; Это позволит Exchange самостоятельно представлять себе и всех авторизованных пользователей в сфере. Например:
  
```
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Кроме того, вы можете создать партнерское приложение, скопировав и изменив код сценария, который находится в документации для проверки подлинности сервера в Skype для бизнеса Server. Дополнительные сведения можно найти в статье [Управление проверкой подлинности серверов (OAuth) и партнерских программ в Skype для бизнеса Server](../../manage/authentication/server-to-server-and-partner-applications.md) .
  
Если вы успешно настроили партнерские приложения для Skype для бизнеса Server и Exchange Server, вы также успешно настроили проверку подлинности серверов и сервера между двумя продуктами. В Skype для бизнеса Server есть командлет Windows PowerShell [Test-ксекссторажеконнективити](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) , который позволяет проверить правильность настройки проверки подлинности серверов и сервера в службе хранилища Skype для бизнеса Server. Подключитесь к Exchange Server. Командлет делает это, подключаясь к почтовому ящику пользователя Exchange Server, записывая элемент в папку журнала бесед для этого пользователя, а затем (необязательно) его удаление.
  
Чтобы протестировать интеграцию Skype для бизнеса Server и Exchange Server, выполните в командной консоли Skype для Business Server команду, подобную следующей:
  
```
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

В предыдущей команде Сипури — адрес SIP пользователя с учетной записью на сервере Exchange Server; не удается выполнить команду, так как она не является действительной учетной записью пользователя.
  
> [!NOTE]
> Если вы получили ответ 401 от этого командлета, скорее всего, это связано с тем, что в конфигурации Exchange по умолчанию не указана поддержка приема маркеров OAuth. Дополнительные сведения об использовании OAuth в Exchange можно найти в разделе [Настройка проверки подлинности OAuth с помощью SharePoint 2013 и Skype для бизнеса Server](https://go.microsoft.com/fwlink/p/?LinkId=513103). 
  
Если проверка завершилась успешно и соединение было установлено, можно перейти к настройке дополнительных компонентов, таких как интеграция службы архивации и единое хранилище контактов.
