---
title: Настройка интеграции между локальной Skype для бизнеса Server и Outlook Web App
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: Сводка. Интеграция Skype для бизнеса Server и Outlook Web App.
ms.openlocfilehash: 0284fee227d9adf5560b5f65e56d71c1d46fac0c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397295"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Настройка интеграции между локальной Skype для бизнеса Server и Outlook Web App

**Сводка:** Интеграция Skype для бизнеса Server и Outlook Web App.

Клиенты, использующие локальное Skype для бизнеса Server развертывания, могут настраивать Microsoft Outlook Web App в Microsoft Exchange Online в режиме гибридного развертывания. Возможности взаимодействия включают единый вход и интеграцию обмена мгновенными сообщениями и сведениями о присутствии в интерфейс Outlook Web App. Чтобы включить эту интеграцию, необходимо настроить edge Server в локальном Skype для бизнеса Server развертывания, выполняя следующие задачи:

- настройте общее адресное пространство SIP;

- Настройка поставщика хостинга на edge Server

- Проверка репликации обновленного центра управления

## <a name="configure-a-shared-sip-address-space"></a>Настройка общего адресного пространства SIP

Чтобы интегрировать локальное Skype для бизнеса Server с Exchange Online, необходимо настроить общее адресное пространство SIP. Одно и то же пространство адресов домена SIP поддерживается как Skype для бизнеса Server, так и Exchange Online службой.

С помощью Skype для бизнеса Server управленческой оболочки настройте edge Server для федерации с помощью команды **Set-CSAccessEdgeConfiguration**, используя параметры, отображаемые в следующем примере:

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- Параметр **AllowFederatedUsers** указывает, разрешено ли внутренним пользователям связываться с пользователями из федеративных доменов. Это свойство также определяет, могут ли внутренние пользователи общаться с пользователями в совместном сценарии адресного пространства SIP с Skype для бизнеса Server и Exchange Online.

Подробные сведения об использовании Skype для бизнеса Server управления см. в [Skype для бизнеса Server Management Shell](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Настройка поставщика услуг размещения на пограничном сервере

С помощью Skype для бизнеса Server management Shell настройте поставщика хостинга на edge Server, заняв команды **New-CsHostingProvider**, используя параметры в следующем примере:

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Если вы используете Microsoft 365 или Office 365 21Vianet в Китае, замените значение параметра ProxyFqdn в этом примере ("exap.um.outlook.com") FQDN для службы, выполняемой 21Vianet: "exap.um.partner.outlook.cn". Если вы используете Microsoft 365 или Office 365 GCC High, замените значение параметра ProxyFqdn в этом примере ("exap.um.outlook.com") на FQDN для GCC High: "exap.um.office365.us".

- Параметр **Identity** определяет строковое значение уникального идентификатора для создаваемого поставщика услуг размещения (например, "Exchange Online"). Значения с пробелами должны заключаться в двойные кавычки.

- Параметр **Enabled** определяет, включено ли сетевое соединение между вашим доменом и поставщиком услуг размещения. Должен иметь значение True.

- Параметр **EnabledSharedAddressSpace** определяет, используется ли поставщик услуг размещения в общем адресном пространстве SIP. Должен иметь значение True.

- **HostsOCSUsers** указывает, используется ли поставщик хостинга для размещения Office или Skype для бизнеса Server. Должен иметь значение False.

- Параметр **ProxyFQDN** определяет полное доменное имя прокси-сервера, используемого поставщиком услуг размещения. Для Exchange Online полное доменное имя — exap.um.outlook.com.

- **IsLocal** указывает, содержится ли прокси-сервер, используемый поставщиком хостинга, в топологии Skype для бизнеса Server. Должен иметь значение False.

- Параметр **VerificationLevel** указывает разрешенный уровень проверки сообщений, отправляемых поставщику и получаемых от него. Задайте значение **UseSourceVerification**, при котором используется уровень проверки, добавленный в сообщения, отправляемые поставщиком услуг размещения. Если этот уровень не указан, сообщения будут отклоняться как недоступные для проверки.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Проверка репликации обновленного центрального хранилища управления

Изменения, внесенные с помощью cmdlets в предыдущих разделах, автоматически применяются к edge Server и, как правило, для репликации требуется менее минуты. Вы можете проверить состояние репликации, а затем подтвердить, что изменения были применены к вашему edge Server с помощью следующих cmdlets.

Чтобы проверить обновления репликации, на внутреннем сервере в Skype для бизнеса Server развертывания запустите следующий cmdlet:

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

[Предоставление Skype для бизнеса Server голосовой почты пользователей на Exchange um](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[размещенный Exchange интеграции единой системы обмена сообщениями в Skype для бизнеса Server](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)