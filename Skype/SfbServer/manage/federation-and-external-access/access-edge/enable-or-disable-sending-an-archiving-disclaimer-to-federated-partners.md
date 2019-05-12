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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 2478d1f0a8b09fc8d2eff0f3131ad703a3bd72bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919530"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Включение и отключение отправки федеративным партнерам Скайп заявление об отказе для архивации для Business Server

Во время развертывания пограничных серверов и поддержкой федерации для вашей организации должны указаны следует ли автоматически отправлять от архивирования федеративным партнерам. Если архивация внешних коммуникаций, следует включить отправки отказа от архивирования. Используйте описанную в этом разделе для изменения конфигурации.

> [!NOTE]
> В следующей процедуре предполагается, что вы уже включен федерации для вашей организации. Для получения дополнительных сведений о включении федерации видеть [включения или отключения удаленного доступа пользователей](enable-or-disable-remote-user-access.md).


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Включение и отключение отправки отказа от архивирования федеративным партнерам

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server. 

3.  В левой панели навигации щелкните **Доступ для внешних пользователей**, **Настройка пограничного доступа**.

4.  На вкладке **Конфигурация пограничного доступа** последовательно выберите пункты **Глобальная**, **Изменить** и **Показать подробности**.

5.  В разделе **Изменить настройку пограничного доступа**, в разделе **Разрешить связь с федеративными пользователями**установите или снимите флажок **отправлять уведомление об федеративным партнерам архивации** для включения или отключения автоматически отправляя архивации Заявление об отказе.

6.  Нажмите **Исполнить**.

Чтобы разрешить федеративным пользователям совместно работать с пользователями в вашей Скайп для развертывания Business Server, необходимо также настроить по крайней мере одной политики внешнего доступа для поддержки доступа федеративных пользователей. Для получения дополнительных сведений о контроле доступа для определенных федеративных доменов в статье [Configure поддержки для разрешенных внешних доменов](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Включение или отключение архивации заявление об отказе с помощью командлетов Windows PowerShell

Использование от архивирования можно управлять с помощью командлета Set-CsAccessEdgeConfiguration и Windows PowerShell. Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>Включение архивации заявление об отказе

  - Чтобы включить заявление об отказе для архивации, установите для свойства **EnableArchivingDisclaimer** значение True ($True):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>Для отключения от архивирования

  - Чтобы отключить заявление об отказе для архивации, установите для свойства **EnableArchivingDisclaimer** значение False ($False):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


