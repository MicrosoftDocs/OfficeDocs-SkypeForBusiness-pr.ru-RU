---
title: Настройка интеграции между локальной системой Skype для бизнеса Server и Outlook Web App
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Сводка: интеграция Skype для бизнеса Server и Outlook Web App.'
ms.openlocfilehash: ee5676c0dbe88568af78a1c278eea8a46457cb5c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221189"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Настройка интеграции между локальной системой Skype для бизнеса Server и Outlook Web App

**Сводка:** Интеграция Skype для бизнеса Server и Outlook Web App.

Клиенты, использующие локальные развертывания Skype для бизнеса Server, могут настраивать взаимодействие с Microsoft Outlook Web App в Microsoft Exchange Online в режиме гибридного развертывания. Возможности взаимодействия включают единый вход и интеграцию обмена мгновенными сообщениями и сведениями о присутствии в интерфейс Outlook Web App. Чтобы включить эту интеграцию, необходимо настроить пограничный сервер в локальном развертывании Skype для бизнеса Server, выполнив следующие действия:

- настройте общее адресное пространство SIP;

- Настройка поставщика услуг хостинга на пограничном сервере

- Проверка репликации обновленного центрального хранилища управления

## <a name="configure-a-shared-sip-address-space"></a>Настройка общего адресного пространства SIP

Чтобы интегрировать локальную среду Skype для бизнеса Server с Exchange Online, необходимо настроить общее адресное пространство SIP. Одно и то же адресное пространство домена SIP поддерживается как в Skype для бизнеса Server, так и в службе Exchange Online.

Используя командную консоль Skype для бизнеса Server, настройте пограничный сервер для Федерации, выполнив командлет **Set-CSAccessEdgeConfiguration** с использованием параметров, показанных в следующем примере:

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- Параметр **AllowFederatedUsers** указывает, разрешено ли внутренним пользователям связываться с пользователями из федеративных доменов. Это свойство также определяет, могут ли внутренние пользователи связываться с пользователями в общем адресном пространстве SIP с помощью Skype для бизнеса Server и Exchange Online.

Дополнительные сведения об использовании командной консоли Skype для бизнеса Server можно найти в [консоли управления Skype для бизнеса](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Настройка поставщика услуг размещения на пограничном сервере

С помощью командной консоли Skype для бизнеса Server настройте поставщик услуг хостинга на пограничном сервере, выполнив командлет **New-CsHostingProvider** с использованием параметров, приведенных в следующем примере:

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Если вы используете Microsoft 365 или Office 365 под управлением 21Vianet в Китае, замените значение параметра ProxyFqdn в этом примере ("exap.um.outlook.com") на полное доменное имя службы, обслуживаемой 21Vianet: "exap.um.partner.outlook.cn". Если вы используете Microsoft 365 или Office 365 GCC High, замените значение параметра ProxyFqdn в этом примере ("exap.um.outlook.com") на полное доменное имя для GCC High: "exap.um.office365.us".

- Параметр **Identity** определяет строковое значение уникального идентификатора для создаваемого поставщика услуг размещения (например, "Exchange Online"). Значения с пробелами должны заключаться в двойные кавычки.

- Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения. Должен иметь значение True.

- **EnabledSharedAddressSpace** определяет, используется ли поставщик услуг размещения в общем адресном пространстве SIP. Должен иметь значение True.

- **Хостсоксусерс** указывает, используется ли поставщик услуг размещения для размещения Office Communications Server или Skype для бизнеса Server. Должен иметь значение False.

- Параметр **ProxyFQDN** определяет полное доменное имя прокси-сервера, используемого поставщиком услуг размещения. Для Exchange Online полное доменное имя — exap.um.outlook.com.

- Параметр "... **" указывает,** входит ли прокси-сервер, используемый поставщиком услуг хостинга, в вашу топологию Skype для бизнеса Server. Должен иметь значение False.

- **Верификатионлевел** Указывает уровень проверки, разрешенный для сообщений, отправляемых поставщику услуг размещения и от него. Укажите **UseSourceVerification**, что основывается на уровне проверки, включенном в сообщения, отправленные от поставщика услуг размещения. Если этот уровень не указан, сообщение будет отклонено как Непроверяемое.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Проверка репликации обновленного центрального хранилища управления

Изменения, внесенные с помощью командлетов, описанных в предыдущих разделах, автоматически применяются к пограничным серверам, и для репликации обычно требуется меньше минуты. Вы можете проверить состояние репликации, а затем подтвердить, что изменения были применены к пограничному серверу с помощью следующих командлетов.

Чтобы проверить наличие обновлений репликации на внутреннем сервере в развертывании Skype для бизнеса Server, выполните следующий командлет:

```powershell
Get-CsManagementStoreReplicationStatus
```
Установите флажок, если значение Уптодате отображается как TRUE для всех реплик.

Чтобы убедиться, что изменения применены, на пограничном сервере выполните следующий командлет:

```powershell
Get-CsHostingProvider -LocalStore
```
Дважды проверьте, соответствуют ли отображаемые сведения изменениям, зафиксированным на предыдущих шагах.

## <a name="see-also"></a>См. также

[Предоставление пользователям Skype для бизнеса Server голосовой почты в размещенной единой системе обмена сообщениями Exchange](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Интеграция единой системы обмена сообщениями Exchange в Skype для бизнеса Server](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
