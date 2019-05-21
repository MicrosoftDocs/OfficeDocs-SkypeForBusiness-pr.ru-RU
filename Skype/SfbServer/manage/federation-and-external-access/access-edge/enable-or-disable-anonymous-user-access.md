---
title: Включение или отключение анонимного доступа пользователей
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: a368a364f39fe8178e9ce4f17a17bea96fea7b23
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280273"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="f923a-102">Включение и отключение анонимного доступа пользователей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f923a-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="f923a-103">Анонимные пользователи — это пользователи, у которых нет учетной записи пользователя в доменных службах Active Directory или в поддерживаемом Федеративной домене, но может быть приглашено удаленно участвовать в локальной конференции.</span><span class="sxs-lookup"><span data-stu-id="f923a-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="f923a-104">Разрешая Анонимное участие в собраниях, вы включаете анонимных пользователей (то есть для пользователей, чьи удостоверения проверяются только с помощью собрания или ключа конференции) для присоединения к собраниям.</span><span class="sxs-lookup"><span data-stu-id="f923a-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="f923a-105">Разрешение анонимного участия требует ее включения в вашу организацию.</span><span class="sxs-lookup"><span data-stu-id="f923a-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="f923a-106">Если позже вы захотите временно запретить доступ анонимных пользователей к Интернету, вы можете отключить ее для своей организации.</span><span class="sxs-lookup"><span data-stu-id="f923a-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="f923a-107">Чтобы включить или отключить анонимный доступ для пользователей в Организации, выполните действия, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="f923a-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="f923a-108">Включив анонимные пользователи, вы указываете, что серверы, на которых работает служба EDGE, должны поддерживать доступ анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="f923a-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="f923a-109">Анонимные пользователи не могут принимать участие в собраниях в вашей организации, пока не будет настроена хотя бы одна политика Конференции и она будет применена к одному или нескольким пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="f923a-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="f923a-110">Пользователи, которые могут пригласить анонимных пользователей на собрания, — это те, которым назначена политика конференций, настроенная для поддержки анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="f923a-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="f923a-111">Дополнительные сведения о настройке политик конференц-связи для анонимных пользователей можно найти в разделе [Управление политиками Конференц](../../conferencing/conferencing-policies.md)-связи.</span><span class="sxs-lookup"><span data-stu-id="f923a-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="f923a-112">Включение и отключение анонимного доступа пользователей к Организации</span><span class="sxs-lookup"><span data-stu-id="f923a-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="f923a-113">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f923a-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f923a-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f923a-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="f923a-115">На панели навигации слева выберите элемент **внешний доступ к пользователю**, а затем — **Конфигурация Edge Access**.</span><span class="sxs-lookup"><span data-stu-id="f923a-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="f923a-116">На странице **конфигурации Edge Access** щелкните **Глобальная**, выберите пункт **изменить**, а затем — **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="f923a-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f923a-117">В окне **изменение конфигурации Edge Access**выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f923a-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="f923a-118">Чтобы включить анонимный доступ для пользователей в Организации, установите флажок **включить связь с анонимными пользователями** .</span><span class="sxs-lookup"><span data-stu-id="f923a-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="f923a-119">Чтобы запретить анонимный доступ к Организации, снимите флажок **включить связь с анонимными пользователями** .</span><span class="sxs-lookup"><span data-stu-id="f923a-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="f923a-120">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="f923a-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f923a-121">Включение и отключение анонимного доступа пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f923a-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f923a-122">Управлять доступом анонимных пользователей можно с помощью Windows PowerShell и командлета **Set-ксакцесседжеконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="f923a-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="f923a-123">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f923a-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="f923a-124">Разрешение анонимного доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="f923a-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="f923a-125">Чтобы включить анонимный доступ для пользователей, присвойте свойству **аллованонимаусусерс** значение True ($true):</span><span class="sxs-lookup"><span data-stu-id="f923a-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="f923a-126">Отключение анонимного доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="f923a-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="f923a-127">Чтобы запретить анонимный доступ пользователей, установите для свойства **аллованонимаусусерс** значение False ($false):</span><span class="sxs-lookup"><span data-stu-id="f923a-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="f923a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="f923a-128">See Also</span></span>

[<span data-ttu-id="f923a-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="f923a-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
