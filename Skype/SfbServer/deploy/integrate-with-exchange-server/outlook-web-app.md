---
title: Настройка интеграции между локальной skype для бизнеса Server и Outlook Web App
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Сводка. Интеграция Skype для бизнеса Server и Outlook Web App.
ms.openlocfilehash: daa9430034d82a3a8dee980a9b075b2fc5656c86
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109695"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Настройка интеграции между локальной skype для бизнеса Server и Outlook Web App

**Сводка:** Интеграция Skype для бизнеса Server и Outlook Web App.

Клиенты, использующие локальное развертывание Skype для бизнеса Server, могут настраивать Microsoft Outlook Web App в Microsoft Exchange Online в гибридном режиме развертывания. Возможности взаимодействия включают единый вход и интеграцию обмена мгновенными сообщениями и сведениями о присутствии в интерфейс Outlook Web App. Чтобы включить эту интеграцию, необходимо настроить edge Server в локальном развертывании Skype для бизнеса, завершив следующие задачи:

- настройте общее адресное пространство SIP;

- Настройка поставщика хостинга на edge Server

- Проверка репликации обновленного центра управления

## <a name="configure-a-shared-sip-address-space"></a>Настройка общего адресного пространства SIP

Чтобы интегрировать локальное пространство Skype для бизнеса Server с Exchange Online, необходимо настроить общее пространство адресов SIP. Одно и то же пространство адресов домена SIP поддерживается как Skype для бизнеса Server, так и службой Exchange Online.

С помощью оболочки управления Skype для бизнес-серверов настройте edge Server для федерации, используя команды **set-CSAccessEdgeConfiguration,** используя параметры, отображаемые в следующем примере:

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- Параметр **AllowFederatedUsers** указывает, разрешено ли внутренним пользователям связываться с пользователями из федеративных доменов. Это свойство также определяет, могут ли внутренние пользователи общаться с пользователями в сценарии общего пространства адресов SIP в Skype для бизнеса Server и Exchange Online.

Сведения об использовании оболочки управления Skype для бизнес-серверов см. в [материале Skype for Business Server Management Shell.](../../manage/management-shell.md)

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Настройка поставщика услуг размещения на пограничном сервере

Используя оболочку управления Skype для бизнес-серверов, настройте поставщика хостинга на edge Server, заняв команды **New-CsHostingProvider,** используя параметры в следующем примере:

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Если вы используете Microsoft 365 или Office 365 под управлением 21Vianet в Китае, замените значение параметра ProxyFqdn в этом примере ("exap.um.outlook.com") на FQDN для службы, выполняемой 21Vianet: "exap.um.partner.outlook.cn". Если вы используете Microsoft 365 или Office 365 GCC High, замените значение параметра ProxyFqdn в этом примере ("exap.um.outlook.com") на FQDN для GCC High: "exap.um.office365.us".

- Параметр **Identity** определяет строковое значение уникального идентификатора для создаваемого поставщика услуг размещения (например, "Exchange Online"). Значения с пробелами должны заключаться в двойные кавычки.

- Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения. Должен иметь значение True.

- **EnabledSharedAddressSpace** определяет, используется ли поставщик услуг размещения в общем адресном пространстве SIP. Должен иметь значение True.

- **HostsOCSUsers** указывает, используется ли поставщик хостинга для размещения office Communications Server или Skype для бизнеса Server. Должен иметь значение False.

- Параметр **ProxyFQDN** определяет полное доменное имя прокси-сервера, используемого поставщиком услуг размещения. Для Exchange Online полное доменное имя — exap.um.outlook.com.

- **IsLocal указывает,** содержится ли прокси-сервер, используемый поставщиком хостинга, в топологии Skype для бизнеса Server. Должен иметь значение False.

- **VerificationLevel** Указывает уровень проверки, разрешенный для сообщений, отосланных в и от принимающего поставщика. Укажите **UseSourceVerification**, что основывается на уровне проверки, включенном в сообщения, отправленные от поставщика услуг размещения. Если этот уровень не указан, сообщение будет отклонено как непроверяемое.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Проверка репликации обновленного центрального хранилища управления

Изменения, внесенные с помощью cmdlets в предыдущих разделах, автоматически применяются к edge Server и, как правило, для репликации требуется менее минуты. Вы можете проверить состояние репликации, а затем подтвердить, что изменения были применены к вашему edge Server с помощью следующих cmdlets.

Чтобы проверить обновления репликации на внутреннем сервере в развертывании Skype для бизнеса Server, запустите следующий cmdlet:

```powershell
Get-CsManagementStoreReplicationStatus
```
Проверьте, отображается ли значение UpToDate TRUE для всех реплик.

Чтобы подтвердить, что изменения были применены, на edge Server запустите следующий cmdlet:

```powershell
Get-CsHostingProvider -LocalStore
```
Дважды проверьте, соответствует ли показанная информация изменениям, совершенным на предыдущих действиях.

## <a name="see-also"></a>См. также

[Предоставление голосовой почты пользователей Skype для бизнеса Server в ХОЗ Exchange](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[Интеграция единой системы обмена сообщениями Exchange в Skype для бизнеса Server](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)