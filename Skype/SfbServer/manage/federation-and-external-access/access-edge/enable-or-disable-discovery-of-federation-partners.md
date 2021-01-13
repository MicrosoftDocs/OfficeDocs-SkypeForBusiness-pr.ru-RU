---
title: Включение или отключение обнаружения федеративных партнеров
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Во время развертывания пограничных серверов и включения федерации для организации необходимо указать, должно ли поддерживаться автоматическое обнаружение федеративных доменов партнеров.
ms.openlocfilehash: e1f076b725dff149f024a3fd59f9f7d52da4e6a8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817429"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Enable or disable discovery of federation partners in Skype for Business Server

Во время развертывания пограничных серверов и включения федерации для организации необходимо указать, должно ли поддерживаться автоматическое обнаружение федеративных доменов партнеров. Используйте процедуру, описанную в данном разделе, для изменения этой конфигурации.

> [!NOTE]  
> В следующей процедуре предполагается, что федерация уже включена для организации. Подробные сведения о включаемой федерации см. в сведениях о [включаемом или отключаемом удаленном доступе пользователей.](enable-or-disable-remote-user-access.md)

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Включение или отключение автоматического обнаружения федеративных доменов для организации

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.

3.  В левой панели навигации щелкните **Доступ для внешних пользователей** и **Настройка пограничного доступа**.

4.  На странице **Настройка пограничного доступа** выберите пункты **Глобальная** и **Изменить**, а затем щелкните **Подробнее**.

5.  В разделе **Изменить настройку пограничного доступа** в области **Разрешить взаимодействие с федеративными пользователями** установите или снимите флажок **Разрешить обнаружение домена партнера**, чтобы включить или отключить автоматическое обнаружение доменов партнеров.

6.  Нажмите кнопку **Сохранить**.

Чтобы позволить федератным пользователям взаимодействовать с пользователями в развертывании Skype для бизнеса Server, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки доступа федераированных пользователей. Подробные сведения см. в [подключите или отключите федерацию и подключение к общедоступным системам im.](enable-or-disable-federation-and-public-im-connectivity.md) Подробные сведения об управлении доступом для определенных федераированных доменов см. в подтипе "Управление федератными [доменами SIP"](../sip-domains/manage-sip-federated-domains-for-your-organization.md) и "Управление федератными [поставщиками SIP".](../sip-providers/manage-sip-federated-providers-for-your-organization.md)


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Включение или отключение обнаружения партнеров федерации с помощью Windows PowerShell управления

Обнаружением партнеров федерации можно управлять с помощью Windows PowerShell и Set-CsAccessEdgeConfiguration управления. Этот cmdlet можно запустить либо из оболочки управления Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. 


## <a name="to-enable-discovery-of-federation-partners"></a>Чтобы включить обнаружение федератных партнеров

  - Чтобы включить обнаружение федеративных партнеров, задайте для свойства **EnablePartnerDiscovery** значение True ($True). Обратите внимание, что для изменения значения этого свойства необходимо включить маршрутизацию DNS SRV.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>Отключение обнаружения федератных партнеров

  - Чтобы отключить обнаружение федеративных партнеров, задайте для свойства **EnablePartnerDiscovery** значение False ($False).
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

