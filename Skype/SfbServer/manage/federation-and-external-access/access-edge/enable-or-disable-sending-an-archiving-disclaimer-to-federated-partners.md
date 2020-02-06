---
title: Включение и отключение отправки отказа от архивирования федеративным партнерам
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 889716377f89e2657adcd6e32c9077b8124e20c1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818360"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Включение и отключение отправки заявления об отказе на архивацию федеративных партнеров в Skype для бизнеса Server

На момент развертывания пограничных серверов и включения Федерации для Организации необходимо указать, следует ли автоматически отправлять заявление об отказе от архивации федеративным партнерам. При архивации внешних данных необходимо включить отправку сообщений об отказе в архивацию. Чтобы изменить конфигурацию, воспользуйтесь процедурой, описанной в этом разделе.

> [!NOTE]
> В описанной ниже процедуре предполагается, что вы уже включили Федерацию для своей организации. Дополнительные сведения о включении Федерации можно найти в разделе [Включение и отключение удаленного доступа пользователей](enable-or-disable-remote-user-access.md).


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Включение и отключение отправки запроса на архивацию федеративных партнеров

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 

3.  На панели навигации слева выберите **внешний пользовательский доступ**, а затем — **Конфигурация Edge Access**.

4.  На вкладке **Конфигурация пограничного доступа** последовательно выберите пункты **Глобальная**, **Изменить** и **Показать подробности**.

5.  В диалоговом окне **изменение конфигурации Edge для доступа**в разделе **включить связь с федеративными пользователями**установите или снимите флажок **отправлять заявление об отказе от работы федеративным партнерам** , чтобы включить или отключить автоматическую отправку сообщений об отказе в архивацию.

6.  Нажмите **Исполнить**.

Чтобы пользователи федеративных пользователей могли работать с пользователями в развертывании Skype для бизнеса Server, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки федеративного доступа пользователей. Дополнительные сведения об управлении доступом для определенных федеративных доменов см. в разделе [Настройка поддержки для разрешенных внешних доменов](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Включение и отключение отказа от архивации с помощью командлетов Windows PowerShell

Для управления использованием отказа в архивации можно использовать Windows PowerShell и командлет Set-Ксакцесседжеконфигуратион. Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>Включение отказа в архивации

  - Чтобы включить заявление об отказе для архивации, установите для свойства **EnableArchivingDisclaimer** значение True ($True):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>Отключение отказа от архивации

  - Чтобы отключить заявление об отказе для архивации, установите для свойства **EnableArchivingDisclaimer** значение False ($False):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


