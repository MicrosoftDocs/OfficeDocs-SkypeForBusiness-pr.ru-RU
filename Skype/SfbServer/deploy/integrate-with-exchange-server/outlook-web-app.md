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
ms.openlocfilehash: 0a6358c93356bd059aeed34033b07916d856bf10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833969"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Настройка интеграции между локальной skype для бизнеса Server и Outlook Web App

**Сводка:** Интеграция Skype для бизнеса Server и Outlook Web App.

Клиенты, использующие локальное развертывание Skype для бизнеса Server, могут настроить Microsoft Outlook Web App в Microsoft Exchange Online в режиме гибридного развертывания. Возможности взаимодействия включают единый вход и интеграцию обмена мгновенными сообщениями и сведениями о присутствии в интерфейс Outlook Web App. Чтобы включить эту интеграцию, необходимо настроить edge Server в локальном развертывании Skype для бизнеса Server, выполив следующие задачи:

- настройте общее адресное пространство SIP;

- Настройка поставщика услуг размещения на edge Server

- Проверка репликации обновленного центрального банка управления

## <a name="configure-a-shared-sip-address-space"></a>Настройка общего адресного пространства SIP

Чтобы интегрировать локальное приложение Skype для бизнеса Server с Exchange Online, необходимо настроить общее адресное пространство SIP. Одно и то же адресное пространство домена SIP поддерживается и Skype для бизнеса Server, и службой Exchange Online.

С помощью оболочки управления Skype для бизнеса Server настройте для федерационного сервера с помощью команды **Set-CSAccessEdgeConfiguration,** используя параметры, показанные в следующем примере:

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- Параметр **AllowFederatedUsers** указывает, разрешено ли внутренним пользователям связываться с пользователями из федеративных доменов. Это свойство также определяет, могут ли внутренние пользователи взаимодействовать с пользователями в общем адресном пространстве SIP со Skype для бизнеса Server и Exchange Online.

For details about using the Skype for Business Server Management Shell, see [Skype for Business Server Management Shell.](../../manage/management-shell.md)

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Настройка поставщика услуг размещения на пограничном сервере

С помощью оболочки управления Skype для бизнеса Server настройте поставщика услуг размещения на edge-сервере с помощью команды **New-CsHostingProvider,** используя параметры в следующем примере:

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Если вы используете Microsoft 365 или Office 365 под управлением 21Vianet в Китае, замените значение параметра ProxyFqdn в этом примере ("exap.um.outlook.com") на FQDN службы, под управлением 21Vianet: "exap.um.partner.outlook.cn". Если вы используете Microsoft 365 или Office 365 GCC High, замените значение параметра ProxyFqdn в этом примере ("exap.um.outlook.com") на FQDN для GCC High: "exap.um.office365.us".

- Параметр **Identity** определяет строковое значение уникального идентификатора для создаваемого поставщика услуг размещения (например, "Exchange Online"). Значения с пробелами должны заключаться в двойные кавычки.

- Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения. Должен иметь значение True.

- **EnabledSharedAddressSpace** определяет, используется ли поставщик услуг размещения в общем адресном пространстве SIP. Должен иметь значение True.

- **HostsOCSUsers** указывает, используется ли поставщик услуг размещения для размещения Office Communications Server или Skype для бизнеса Server. Должен иметь значение False.

- Параметр **ProxyFQDN** определяет полное доменное имя прокси-сервера, используемого поставщиком услуг размещения. Для Exchange Online полное доменное имя — exap.um.outlook.com.

- **IsLocal** указывает, содержится ли прокси-сервер, используемый поставщиком услуг размещения, в топологии Skype для бизнеса Server. Должен иметь значение False.

- **VerificationLevel** Указывает допустимый уровень проверки для сообщений, от отправленных поставщику услуг и от него. Укажите **UseSourceVerification**, что основывается на уровне проверки, включенном в сообщения, отправленные от поставщика услуг размещения. Если этот уровень не указан, сообщение будет отклонено как непроверенное.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Проверка репликации обновленного центрального хранилища управления

Изменения, внесенные с помощью предыдущих разделов, автоматически применяются к серверу и обычно репликируются менее чем за минуту. Вы можете проверить состояние репликации, а затем подтвердить, что изменения были применены к вашему серверу, с помощью следующих cmdlets.

Чтобы проверить обновления репликации, на внутреннем сервере в развертывании Skype для бизнеса Server запустите следующий cmdlet:

```powershell
Get-CsManagementStoreReplicationStatus
```
Проверьте, отображается ли значение UpToDate true для всех реплик.

Чтобы подтвердить внесение изменений, на edge Server запустите следующий cmdlet:

```powershell
Get-CsHostingProvider -LocalStore
```
Убедитесь, что показанная информация соответствует изменениям, внесенным на предыдущих шагах.

## <a name="see-also"></a>См. также

[Предоставление пользователям Skype для бизнеса Server голосовой почты в сервере exchange UM](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Интеграция с единой системы обмена сообщениями Exchange в Skype для бизнеса Server](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
