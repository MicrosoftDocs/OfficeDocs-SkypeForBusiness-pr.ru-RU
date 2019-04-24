---
title: Включение или отключение анонимного доступа пользователей
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: a68790f870a6c62b513caab559580695763cd4df
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199950"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="2661d-102">Включение и отключение анонимного доступа пользователей в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="2661d-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="2661d-103">Анонимные пользователи не пользователей, у которых нет учетной записи пользователя в доменных службах Active Directory вашей организации или в поддерживаемых федеративного домена, но можно пригласить для участия в конференции в режиме локальной удаленно.</span><span class="sxs-lookup"><span data-stu-id="2661d-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="2661d-104">Посредством создания анонимного участия в собраниях разрешить анонимным пользователям (то есть пользователи, идентификатор которого проверяется через собрания или конференции ключ) для присоединения к собраниям.</span><span class="sxs-lookup"><span data-stu-id="2661d-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="2661d-105">Разрешение анонимного участия требуется включение для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2661d-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="2661d-106">Если позднее вы хотите временно или окончательно запретить доступ анонимных пользователей, его можно отключить для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2661d-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="2661d-107">Используйте процедуру в этом разделе Включение и отключение анонимного доступа пользователей для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="2661d-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="2661d-108">Посредством включения анонимного доступа пользователей для своей организации только указывается, что серверы, где выполняется служба пограничного сервера доступа поддерживают доступ анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="2661d-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="2661d-109">Анонимные пользователи не могут участвовать в любой собраний в вашей организации, пока вы также настроить по крайней мере одна политика конференц-связи и применяются к пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="2661d-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="2661d-110">Только для пользователей, которые можно приглашать на собрания анонимных пользователей — это пользователи, назначенные политики конференц-связи, которая настроена для поддержки анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="2661d-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="2661d-111">Подробные сведения о настройке политик конференц-связи для поддержки приглашать анонимных пользователей содержатся в разделе [Управление политики конференц-связи](../../conferencing/conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2661d-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="2661d-112">Включение и отключение анонимного доступа пользователей для вашей организации</span><span class="sxs-lookup"><span data-stu-id="2661d-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="2661d-113">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2661d-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2661d-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="2661d-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2661d-115">В левой панели навигации щелкните **Доступ для внешних пользователей**и нажмите кнопку **Настройка пограничного доступа**.</span><span class="sxs-lookup"><span data-stu-id="2661d-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="2661d-116">На странице **Настройка пограничного доступа** щелкните **Глобальная**, нажмите кнопку **Изменить**и нажмите кнопку **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="2661d-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2661d-117">В **Изменить настройку пограничного доступа**выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="2661d-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="2661d-118">Чтобы включить анонимный доступ пользователей для вашей организации, установите флажок **Разрешить взаимодействие с анонимными пользователями** .</span><span class="sxs-lookup"><span data-stu-id="2661d-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="2661d-119">Чтобы отключить анонимный доступ пользователей для вашей организации, снимите флажок **Разрешить взаимодействие с анонимными пользователями** .</span><span class="sxs-lookup"><span data-stu-id="2661d-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="2661d-120">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="2661d-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2661d-121">Включение или отключение анонимного доступа пользователей с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2661d-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="2661d-122">Анонимный доступ пользователей можно управлять с помощью командлета **Set-CsAccessEdgeConfiguration** и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2661d-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="2661d-123">Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2661d-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="2661d-124">Чтобы включить анонимный доступ пользователей</span><span class="sxs-lookup"><span data-stu-id="2661d-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="2661d-125">Чтобы включить анонимный доступ пользователей, задайте значение для свойства **AllowAnonymousUsers** значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="2661d-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="2661d-126">Чтобы отключить анонимный доступ пользователей</span><span class="sxs-lookup"><span data-stu-id="2661d-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="2661d-127">Чтобы отключить анонимный доступ пользователей, задайте значение для свойства **AllowAnonymousUsers** значение False ($False):</span><span class="sxs-lookup"><span data-stu-id="2661d-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="2661d-128">См. также</span><span class="sxs-lookup"><span data-stu-id="2661d-128">See Also</span></span>

[<span data-ttu-id="2661d-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="2661d-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
