---
title: Включение или отключение обнаружения федеративных партнеров
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Во время развертывания пограничных серверов и поддержкой федерации для вашей организации должны указаны ли поддержка автоматического обнаружения доменов федеративного партнера.
ms.openlocfilehash: cf12190b03df30f4a15f6ed5e0499aa97c66e576
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919516"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Включение и отключение обнаружения федеративных партнеров в Скайп для Business Server

Во время развертывания пограничных серверов и поддержкой федерации для вашей организации должны указаны ли поддержка автоматического обнаружения доменов федеративного партнера. Используйте описанную в этом разделе для изменения конфигурации.

> [!NOTE]  
> В следующей процедуре предполагается, что вы уже включен федерации для вашей организации. Для получения дополнительных сведений о включении федерации видеть [включения или отключения удаленного доступа пользователей](enable-or-disable-remote-user-access.md).

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Чтобы включить или отключить автоматическое обнаружение федеративных доменов для вашей организации

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.

3.  В левой панели навигации щелкните **Доступ для внешних пользователей**, **Настройка пограничного доступа**.

4.  На странице **Настройка пограничного доступа** щелкните **Глобальная**, нажмите кнопку **Изменить**и нажмите кнопку **Показать подробности**.

5.  В разделе **Изменить настройку пограничного доступа**, в разделе **Разрешить связь с федеративными пользователями**установите или снимите флажок **Разрешить обнаружение домена партнера** , чтобы включить или отключить автоматическое обнаружение доменов партнеров.

6.  Нажмите **Исполнить**.

Чтобы разрешить федеративным пользователям совместно работать с пользователями в вашей Скайп для развертывания Business Server, необходимо также настроить по крайней мере одной политики внешнего доступа для поддержки доступа федеративных пользователей. Дополнительные сведения см [Включить или отключить федерацию и общедоступные службы обмена Мгновенными сообщениями](enable-or-disable-federation-and-public-im-connectivity.md). Для получения дополнительных сведений о контроле доступа для определенных федеративных доменов видеть [Управление SIP федеративных доменов](../sip-domains/manage-sip-federated-domains-for-your-organization.md) и [Управление SIP федеративных поставщиков](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Включение или отключение обнаружения федеративных партнеров с помощью командлетов Windows PowerShell

Обнаружение федеративных партнеров можно управлять с помощью командлета Set-CsAccessEdgeConfiguration и Windows PowerShell. Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell. 


## <a name="to-enable-discovery-of-federation-partners"></a>Чтобы включить обнаружение федеративных партнеров

  - Чтобы включить обнаружение федеративных партнеров, задайте значение свойства **EnablePartnerDiscovery** значение True ($True). Обратите внимание на то, что необходимо включить DNS SRV маршрутизации, чтобы изменить значение этого свойства.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>Чтобы отключить обнаружение федеративных партнеров

  - Чтобы отключить обнаружение федеративных партнеров, задайте значение свойства **EnablePartnerDiscovery** значение False ($False):
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

