---
title: Настройка интеграции между локальной Скайп для Business Server и Outlook Web App
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/7/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Сводка: Интеграция Скайп для Business Server и Outlook Web App.'
ms.openlocfilehash: 3bd5131fcdba3d3253021c711910b18f46e93ce4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884872"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Настройка интеграции между локальной Скайп для Business Server и Outlook Web App

**Сводка:** Интеграция Скайп для Business Server и Outlook Web App.

Пользователи, которые с помощью локального Скайп для развертываний Business Server можно настроить взаимодействие с Microsoft Outlook Web App в Microsoft Exchange Online в режиме гибридного развертывания. Возможности взаимодействия включают единый вход и интеграцию обмена мгновенными сообщениями и сведениями о присутствии в интерфейс Outlook Web App. Для включения этой интеграции, необходимо настроить пограничный сервер в вашей локальной Скайп для развертывания Business Server, выполнив следующие задачи:

- настройте общее адресное пространство SIP;

- Настройка поставщика услуг размещения на пограничном сервере

- Проверка репликации обновленного центрального хранилища управления

## <a name="configure-a-shared-sip-address-space"></a>Настройка общего адресного пространства SIP

Для интеграции локальной Скайп для Business Server с Exchange Online, необходимо настроить общее адресное пространство SIP. Одном адресном пространстве SIP домена поддерживается Скайп для Business Server и службы Exchange Online.

Использование Скайп для консоли Business Server, Настройка пограничного сервера для федерации, выполнив командлет **Set-CSAccessEdgeConfiguration** с использованием параметров, показанных в следующем примере:

```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- Параметр **AllowFederatedUsers** указывает, разрешено ли внутренним пользователям связываться с пользователями из федеративных доменов. Кроме того, это свойство определяет ли внутренние пользователи могут общаться с пользователями в общей сценария пространства адресов SIP с помощью Скайп для Business Server и Exchange Online.

Для получения дополнительных сведений об использовании Скайп для консоли Business Server см [Скайп для консоли Business Server](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Настройка поставщика услуг размещения на пограничном сервере

С помощью Скайп для консоли Business Server настройте поставщика услуг размещения на пограничном сервере, выполнив командлет **New-CsHostingProvider** , с помощью параметров в следующем примере:

```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> При использовании Office 365 под управлением 21Vianet в Китае замените значение для параметра ProxyFqdn (например, exap.um.outlook.com) на полное доменное имя для службы под управлением 21Vianet: "exap.um.partner.outlook.cn". Если вы используете Office 365 GCC высокой, замените значение для параметра ProxyFqdn в этом примере («exap.um.outlook.com») полное доменное имя для высокой GCC: «exap.um.office365.us».

- Параметр **Identity** определяет строковое значение уникального идентификатора для создаваемого поставщика услуг размещения (например, "Exchange Online"). Значения с пробелами должны заключаться в двойные кавычки.

- Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения. Должен иметь значение True.

- Параметр **EnabledSharedAddressSpace** определяет, используется ли поставщик услуг размещения в общем адресном пространстве SIP. Должен иметь значение True.

- **HostsOCSUsers** указывает, используется ли поставщик услуг размещения для размещения для сервера Office Communications Server или Скайп. Должен иметь значение False.

- Параметр **ProxyFQDN** определяет полное доменное имя прокси-сервера, используемого поставщиком услуг размещения. Полное доменное имя Exchange Online: exap.um.outlook.com.

- **IsLocal** указывает, содержится ли прокси-сервер, используемый поставщиком услуг размещения в вашей Скайп для топологии Business Server. Должен иметь значение False.

- **VerificationLevel** Указывает уровень проверки, разрешенных для сообщений, отправленных в и из размещенного в узле поставщика. Укажите параметр **UseSourceVerification**, который основывается на уровне проверки, включенном в сообщения, отправленные от поставщика услуг размещения. Если этот уровень не указан, будет отклонено, как непроверяемый.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Проверка репликации обновленного центрального хранилища управления

Изменения, внесенные с помощью командлетов в предыдущих разделах автоматически применяются на пограничный сервер и обычно занять менее минуты для репликации. Можно проверить состояние репликации и затем убедиться, что были ли применены изменения на пограничный сервер с помощью следующих командлетов.

Проверка обновлений репликации, на внутреннем вашей Скайп для развертывания Business Server, выполните следующий командлет:

```
Get-CsManagementStoreReplicationStatus
```
Установите флажок, если значение UpToDate, на котором отображается значение TRUE для всех реплик.

Чтобы убедиться в том, что были ли применены изменения, на пограничном сервере, выполните следующий командлет:

```
Get-CsHostingProvider -LocalStore
```
Проверьте, если сведения, приведенные соответствует изменения на предыдущих шагах.

## <a name="see-also"></a>См. также

[Предоставление Скайп для Business Server пользователи голосовой почты в размещенной Exchange единой системы обмена СООБЩЕНИЯМИ](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Размещенной интеграции единой системы обмена сообщениями Exchange, в Скайп для Business Server](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
