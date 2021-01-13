---
title: Включение и отключение отправки отказа от архивирования федеративным партнерам
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
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
description: ''
ms.openlocfilehash: 1f0238e177e74dc1263208f9a6a350158825d825
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817359"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server

Во время развертывания ваших edge Servers и включения федерации для организации необходимо было укадрять, следует ли автоматически отправлять заявление об отказе от архива федеративным партнерам. Если архивировать внешние коммуникации, следует включить отправку заявление об отказе от архива. Используйте процедуру, описанную в данном разделе, для изменения этой конфигурации.

> [!NOTE]
> В следующей процедуре предполагается, что федерация уже включена для организации. Подробные сведения о включаемой федерации см. в сведениях о [включаемом или отключаемом удаленном доступе пользователей.](enable-or-disable-remote-user-access.md)


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>Чтобы включить или отключить отправку федеративным партнерам заявление об отказе от архива

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 

3.  В левой панели навигации щелкните **Доступ для внешних пользователей** и **Настройка пограничного доступа**.

4.  На **вкладке "Конфигурация края доступа"** щелкните **"Глобальная",** **"Изменить"** и **"Показать подробности".**

5.  В окне "Изменение конфигурации границы доступа" в области  "Включить связь с федеративными пользователями" выберите или сброзите для федеративных партнеров поле "Отправить заявление об отказе от архивации", чтобы включить или отключить автоматическое отправку заявление об отказе от архивации. 

6.  Щелкните **Исполнить**.

Чтобы позволить федератным пользователям взаимодействовать с пользователями в развертывании Skype для бизнеса Server, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки доступа федераированных пользователей. Подробные сведения об управлении доступом для определенных федераированных доменов см. в подстройке "Настройка поддержки [разрешенных внешних доменов".](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>Включение или отключение заявление об отказе от архива с помощью Windows PowerShell управления

Использованием заявление об отказе от архива можно управлять с помощью Windows PowerShell и Set-CsAccessEdgeConfiguration управления. Этот cmdlet можно запустить либо из оболочки управления Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. 

## <a name="to-enable-the-archiving-disclaimer"></a>Чтобы включить заявление об отказе от архива

  - Чтобы включить заявление об отказе от архива, установите для свойства **EnableArchivingDisclaimer** значение True ($True):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>Отключение заявление об отказе от архива

  - Чтобы отключить заявление об отказе от архива, установите для свойства **EnableArchivingDisclaimer** значение False ($False):
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


