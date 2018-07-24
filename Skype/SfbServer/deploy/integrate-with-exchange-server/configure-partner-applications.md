---
title: Настройка партнерских приложений в Скайп для Business Server 2015 и Exchange Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 'Сводка: Настройка проверки подлинности сервер-сервер для Exchange Server 2016 или Exchange Server 2013 и Скайп для Business Server.'
ms.openlocfilehash: f437b081466f837c012e0d2ddba8bea79d3ad445
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973082"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Настройка партнерских приложений в Скайп Business Server и Exchange Server
 
**Сводка:** Настройка проверки подлинности сервер-сервер для Exchange Server 2016 или Exchange Server 2013 и Скайп для Business Server.
  
Для проверки подлинности "сервер-сервер" обычно требуется два сервера, которые должны обмениваться данными, и сторонний сервер маркеров безопасности. Если сервер A и Server B требуется для связи, затем оба этих серверов обычно сначала общаться с сервера маркеров и получение маркера безопасности доверяют. Затем сервер A отправляет этот маркер безопасности серверу B (и наоборот) в качестве гарантии своей подлинности и надежности.
  
Однако это общее правило. Скайп для Business Server, Exchange Server 2016, Exchange Server 2013 и SharePoint Server 2013 не требуется использовать сервер маркеров сторонних производителей при обмене данными друг с другом; Вот так как эти серверные продукты можно создать маркеров безопасности, которые могут быть приняты с друг с другом без необходимости в отдельном сервере маркеров. (Эта возможность доступна только в Скайп для Business Server, Exchange Server 2016, Exchange Server 2013 и SharePoint Server 2013. Для настройки проверки подлинности "сервер-сервер" с другими серверами, включая серверные продукты Microsoft, потребуется использование стороннего сервера маркеров.)
  
Для настройки проверки подлинности сервер сервер между Скайп для Business Server и Exchange Server необходимо выполнить два действия: 1) необходимо назначить сертификаты на каждом сервере; и, 2) необходимо настроить каждый сервер в качестве партнерского приложения другого сервера:, который означает, что необходимо настроить Скайп для Business Server в качестве партнерского приложения для Exchange Server и необходимо настроить Exchange Server в качестве партнерского приложения для Скайп Business Server.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Настройка Скайп для Business Server в качестве партнерского приложения для Exchange Server

Простой способ настройки Скайп для Business Server в качестве партнерского приложения с Exchange Server 2016 или Exchange Server 2013 — это сценарий Configure-EnterprisePartnerApplication.ps1, сценарий Windows PowerShell, которое поставляется с Exchange Server. Для запуска этого сценария необходимо задать URL-адрес для Скайп для документа метаданных проверки подлинности Business Server; Обычно это будет полное доменное имя Скайп для пула Business Server, а затем /metadata/json/1 суффикс. Например:
  
```
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Для настройки Скайп для Business Server как партнерское приложение, откройте командную консоль Exchange и выполните команду следующего вида (предполагается, что Exchange была установлена на диске C: и что он использует путь к папке по умолчанию).
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

После настройки партнерского приложения рекомендуется остановите и перезапустите Internet Information Services (IIS) на серверах Exchange почтовых ящиков и клиентского доступа. Ниже приведен пример команды перезапуска служб IIS, относящийся к компьютеру atl-exchange-001.
  
```
iisreset atl-exchange-001
```

Эту команду можно выполнить из командной консоли Exchange или из другого командного окна, открытого с правами администратора.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Настройка Exchange Server в качестве партнерского приложения для Скайп для Business Server

После настройки Скайп для Business Server в качестве партнерского приложения для Exchange Server 2016 или Exchange Server 2013, затем необходимо настроить Exchange Server в качестве партнерского приложения для Скайп для Business Server. Это можно сделать с помощью Скайп для консоли Business Server, указав документа метаданных проверки подлинности для Exchange; Обычно это будет URI службы автообнаружения Exchange, а затем /metadata/json/1 суффикс. Например:
  
```
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

В Скайп Business Server с помощью командлета [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) настраиваются партнерских приложений. В дополнение к определению URI метаданных необходимо установить доверие приложения уровня полный; Это позволит Exchange будет представлять себя и любой авторизованный пользователь в сфере. Например:
  
```
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Кроме того можно создать партнерского приложения, копирование и изменение кода скрипта, обнаруженных в Скайп для документации по проверки подлинности сервер сервер Business Server. В статье [Управление проверки подлинности сервер сервер (OAuth) и партнерских приложений в Скайп для Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) для получения дополнительных сведений.
  
Если вы успешно настроили партнерских приложений для обоих Скайп для Business Server и Exchange Server, также успешной настройке проверки подлинности сервер сервер между двумя продуктов. Скайп для Business Server включает в себя командлета Windows PowerShell, [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) , который позволяет проверить правильность настройки проверки подлинности, сервер сервер и, что можно Скайп для службы хранения Business Server Подключитесь к Exchange Server. Командлет делает это подключение к почтовому ящику пользователя с Exchange Server, запись элемента в папке журнала бесед для этого пользователя и (необязательно) Удаление этого элемента.
  
Тестирование интеграции Скайп для Business Server и Exchange Server, выполните команду, аналогичную приведенным ниже, из Скайп для консоли Business Server:
  
```
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

В предыдущей команде SipUri представляет SIP-адрес пользователя с использованием учетной записи на сервере Exchange; команда завершится с ошибкой в это не учетную запись пользователя.
  
> [!NOTE]
> При получении ответа 401 из этого командлета это возможно, так как конфигурация по умолчанию для Exchange не поддерживает за принятие маркеры Oauth. Дополнительные сведения об использовании Oauth в Exchange [OAuth настройки проверки подлинности с помощью SharePoint 2013 и Скайп для Business Server](https://go.microsoft.com/fwlink/p/?LinkId=513103)см. 
  
Если проверка завершилась успешно и соединение было установлено, можно перейти к настройке дополнительных компонентов, таких как интеграция службы архивации и единое хранилище контактов.