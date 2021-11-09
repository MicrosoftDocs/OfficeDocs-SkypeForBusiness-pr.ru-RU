---
title: Включение или отключение обнаружения федеративных партнеров
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Во время развертывания пограничных серверов и включения федерации для организации необходимо указать, должно ли поддерживаться автоматическое обнаружение федеративных доменов партнеров.
ms.openlocfilehash: 4e425566fb0b8aa463c93f0940582487dabaae3d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830013"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a>Включить или отключить обнаружение партнеров федерации в Skype для бизнеса Server

Во время развертывания пограничных серверов и включения федерации для организации необходимо указать, должно ли поддерживаться автоматическое обнаружение федеративных доменов партнеров. Используйте процедуру, описанную в данном разделе, для изменения этой конфигурации.

> [!NOTE]  
> В следующей процедуре предполагается, что федерация уже включена для организации. Сведения о включаемой федерации см. в материале [Включение или отключение удаленного доступа к пользователю.](enable-or-disable-remote-user-access.md)

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Включение или отключение автоматического обнаружения федеративных доменов для организации

1.  С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления.

3.  В левой панели навигации щелкните **Доступ для внешних пользователей** и **Настройка пограничного доступа**.

4.  На странице **Настройка пограничного доступа** выберите пункты **Глобальная** и **Изменить**, а затем щелкните **Подробнее**.

5.  В разделе **Изменить настройку пограничного доступа** в области **Разрешить взаимодействие с федеративными пользователями** установите или снимите флажок **Разрешить обнаружение домена партнера**, чтобы включить или отключить автоматическое обнаружение доменов партнеров.

6.  Нажмите кнопку **Сохранить**.

Чтобы федератированные пользователи могли сотрудничать с пользователями в Skype для бизнеса Server развертывания, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки федератного доступа пользователей. Подробные сведения см. в материале [Enable or disable federation and public IM connectivity.](enable-or-disable-federation-and-public-im-connectivity.md) Сведения об управлении доступом для определенных федераированных доменов см. в материале Управление федерадными доменами [SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) и управление федерадными [поставщиками SIP.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Включение или отключение обнаружения партнеров федерации с помощью Windows PowerShell-

Обнаружение партнеров федерации можно управлять с помощью Windows PowerShell и Set-CsAccessEdgeConfiguration. Этот комлет можно запускать из Skype для бизнеса Server или удаленного сеанса Windows PowerShell. 


## <a name="to-enable-discovery-of-federation-partners"></a>Возможность обнаружения партнеров федерации

  - Чтобы включить обнаружение федеративных партнеров, задайте для свойства **EnablePartnerDiscovery** значение True ($True). Обратите внимание, что для изменения значения этого свойства необходимо включить маршрутизацию DNS SRV.<br/><br/>Set-CsAccessEdgeConfiguration-UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a>Отключение обнаружения партнеров федерации

  - Чтобы отключить обнаружение федеративных партнеров, задайте для свойства **EnablePartnerDiscovery** значение False ($False).<br/><br/>Set-CsAccessEdgeConfiguration-UseDnsSrvRouting -EnablePartnerDiscovery $False

