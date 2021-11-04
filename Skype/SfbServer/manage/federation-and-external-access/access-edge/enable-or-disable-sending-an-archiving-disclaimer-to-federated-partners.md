---
title: Включение и отключение отправки отказа от архивирования федеративным партнерам
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Включите или отключите отправку об отказе от архива федеративным партнерам в Skype для бизнеса Server.
ms.openlocfilehash: 1d3ee9ac1b0f75f9256a16d9ce749fef68736107
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754816"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Включить или отключить отправку об отказе от архива федеративным партнерам в Skype для бизнеса Server

Во время развертывания edge Servers и включенной федерации для вашей организации необходимо было укастерить, следует ли автоматически отправлять отказ от архивизации федеративным партнерам. Если вы архивировать внешние сообщения, следует включить отправку об отказе от архива. Используйте процедуру, описанную в данном разделе, для изменения этой конфигурации.

> [!NOTE]
> В следующей процедуре предполагается, что федерация уже включена для организации. Сведения о включаемой федерации см. в материале [Включение или отключение удаленного доступа к пользователю.](enable-or-disable-remote-user-access.md)


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Чтобы включить или отключить отправку об отказе от архива федеративным партнерам

1.  С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления. 

3.  В левой панели навигации щелкните **Доступ для внешних пользователей** и **Настройка пограничного доступа**.

4.  На **вкладке Конфигурация края** доступа щелкните **Глобальный,** нажмите **кнопку Изменить,** а затем нажмите **показать сведения**.

5.  В **статье Изменение** конфигурации края доступа в статье Включить связь  с федеративными пользователями **выберите** или уберйте отказ от архивации отправки в федеративную проверку партнеров, чтобы включить или отключить автоматически отправку обязвления об отказе от архивации.

6.  Щелкните **Исполнить**.

Чтобы федератированные пользователи могли сотрудничать с пользователями в Skype для бизнеса Server развертывания, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки федератного доступа пользователей. Сведения об управлении доступом к определенным федератным доменам см. в материале [Configure support for allowed external domains.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Включение или отключение отказов от архива с помощью Windows PowerShell-

Использованием обоймы архива можно управлять с помощью Windows PowerShell и Set-CsAccessEdgeConfiguration. Этот комлет можно запускать из Skype для бизнеса Server или удаленного сеанса Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>Чтобы включить отказ от архива

  - Чтобы включить отказ от архива, установите значение свойства **EnableArchivingDisclaimer** true ($True):<br/><br/>Set-CsAccessEdgeConfiguration EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>Отключение отказов от архива

  - Чтобы отключить отказ от архива, установите значение свойства **EnableArchivingDisclaimer** false ($False):<br/><br/>Set-CsAccessEdgeConfiguration EnableArchivingDisclaimer $False

