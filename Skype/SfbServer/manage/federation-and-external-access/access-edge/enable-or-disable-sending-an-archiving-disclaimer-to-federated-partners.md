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
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a><span data-ttu-id="83e89-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="83e89-102">Enable or disable sending an Archiving disclaimer to federated partners in Skype for Business Server</span></span>

<span data-ttu-id="83e89-103">Во время развертывания ваших edge Servers и включения федерации для организации необходимо было укадрять, следует ли автоматически отправлять заявление об отказе от архива федеративным партнерам.</span><span class="sxs-lookup"><span data-stu-id="83e89-103">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="83e89-104">Если архивировать внешние коммуникации, следует включить отправку заявление об отказе от архива.</span><span class="sxs-lookup"><span data-stu-id="83e89-104">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="83e89-105">Используйте процедуру, описанную в данном разделе, для изменения этой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="83e89-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="83e89-106">В следующей процедуре предполагается, что федерация уже включена для организации.</span><span class="sxs-lookup"><span data-stu-id="83e89-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="83e89-107">Подробные сведения о включаемой федерации см. в сведениях о [включаемом или отключаемом удаленном доступе пользователей.](enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="83e89-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="83e89-108">Чтобы включить или отключить отправку федеративным партнерам заявление об отказе от архива</span><span class="sxs-lookup"><span data-stu-id="83e89-108">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="83e89-109">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="83e89-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="83e89-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="83e89-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="83e89-111">В левой панели навигации щелкните **Доступ для внешних пользователей** и **Настройка пограничного доступа**.</span><span class="sxs-lookup"><span data-stu-id="83e89-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="83e89-112">На **вкладке "Конфигурация края доступа"** щелкните **"Глобальная",** **"Изменить"** и **"Показать подробности".**</span><span class="sxs-lookup"><span data-stu-id="83e89-112">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="83e89-113">В окне "Изменение конфигурации границы доступа" в области  "Включить связь с федеративными пользователями" выберите или сброзите для федеративных партнеров поле "Отправить заявление об отказе от архивации", чтобы включить или отключить автоматическое отправку заявление об отказе от архивации. </span><span class="sxs-lookup"><span data-stu-id="83e89-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="83e89-114">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="83e89-114">Click **Commit**.</span></span>

<span data-ttu-id="83e89-115">Чтобы позволить федератным пользователям взаимодействовать с пользователями в развертывании Skype для бизнеса Server, необходимо также настроить по крайней мере одну политику внешнего доступа для поддержки доступа федераированных пользователей.</span><span class="sxs-lookup"><span data-stu-id="83e89-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="83e89-116">Подробные сведения об управлении доступом для определенных федераированных доменов см. в подстройке "Настройка поддержки [разрешенных внешних доменов".](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="83e89-116">For details about controlling access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="83e89-117">Включение или отключение заявление об отказе от архива с помощью Windows PowerShell управления</span><span class="sxs-lookup"><span data-stu-id="83e89-117">Enabling or disabling the archiving disclaimer by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="83e89-118">Использованием заявление об отказе от архива можно управлять с помощью Windows PowerShell и Set-CsAccessEdgeConfiguration управления.</span><span class="sxs-lookup"><span data-stu-id="83e89-118">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="83e89-119">Этот cmdlet можно запустить либо из оболочки управления Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83e89-119">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="83e89-120">Чтобы включить заявление об отказе от архива</span><span class="sxs-lookup"><span data-stu-id="83e89-120">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="83e89-121">Чтобы включить заявление об отказе от архива, установите для свойства **EnableArchivingDisclaimer** значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="83e89-121">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="83e89-122">Отключение заявление об отказе от архива</span><span class="sxs-lookup"><span data-stu-id="83e89-122">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="83e89-123">Чтобы отключить заявление об отказе от архива, установите для свойства **EnableArchivingDisclaimer** значение False ($False):</span><span class="sxs-lookup"><span data-stu-id="83e89-123">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


