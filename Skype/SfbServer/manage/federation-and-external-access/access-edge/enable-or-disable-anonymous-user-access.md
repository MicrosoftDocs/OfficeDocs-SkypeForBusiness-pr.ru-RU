---
title: Включение или отключение анонимного доступа пользователей
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
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
ms.openlocfilehash: 7e828745810bd49f9b8f3ea9e7bee1d023e4fc67
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817449"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="dc5ad-102">Включить или отключить анонимный доступ пользователей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="dc5ad-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="dc5ad-103">Анонимные пользователи — это пользователи, у которых нет учетной записи в доменных службах Active Directory вашей организации или поддерживаемом федератном домене, но они могут быть приглашены на удаленное участие в локальной конференции.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="dc5ad-104">Разрешая анонимное участие в собраниях, вы позволяете анонимным пользователям (удостоверение которых подтверждено только ключом собрания или конференции) присоединяться к собраниям.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="dc5ad-105">Для разрешения анонимного участия необходимо включить его в своей организации.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="dc5ad-p102">Если позднее вам потребуется запретить анонимный доступ пользователей на временной или постоянной основе, вы можете отключить его в своей организации. Используйте приведенную здесь процедуру для включения и отключения анонимного доступа пользователей в своей организации.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-p102">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization. Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="dc5ad-108">Включив анонимный доступ пользователей для своей организации, вы просто указываете, что ваши серверы с пограничной службой доступа поддерживают анонимный доступ пользователей.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="dc5ad-109">Анонимные пользователи не могут участвовать в собраниях вашей организации, пока вы не настроите хотя бы одну политику конференц-связи и не примените ее к одному или нескольким пользователям или группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="dc5ad-110">Приглашать анонимных пользователей на собрания могут только пользователи, которым назначена политика конференц-связи, настроенная для поддержки анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="dc5ad-111">Подробные сведения о настройке политик для поддержки приглашения анонимных пользователей см. в подсети "Управление политиками [для звонков".](../../conferencing/conferencing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="dc5ad-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="dc5ad-112">Включение и отключение анонимного доступа пользователей в своей организации</span><span class="sxs-lookup"><span data-stu-id="dc5ad-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="dc5ad-113">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dc5ad-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="dc5ad-115">В левой панели навигации щелкните **Доступ для внешних пользователей** и **Настройка пограничного доступа**.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="dc5ad-116">На странице **Настройка пограничного доступа** выберите пункты **Глобальная** и **Изменить**, а затем щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="dc5ad-117">В области **Изменение настройки пограничного доступа** выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="dc5ad-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="dc5ad-118">Чтобы включить анонимный доступ пользователей для своей организации, установите флажок **Разрешить взаимодействие с анонимными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="dc5ad-119">Чтобы отключить анонимный доступ пользователей для своей организации, снимите флажок **Разрешить взаимодействие с анонимными пользователями**.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="dc5ad-120">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dc5ad-121">Включение или отключение анонимного доступа пользователей с помощью Windows PowerShell управления</span><span class="sxs-lookup"><span data-stu-id="dc5ad-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="dc5ad-122">Управлять анонимным доступом пользователей можно с помощью Windows PowerShell и с помощью Windows PowerShell **Set-CsAccessEdgeConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="dc5ad-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="dc5ad-123">Вы можете запустить этот Windows PowerShell из оболочки управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="dc5ad-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="dc5ad-124">Чтобы включить анонимный доступ пользователей</span><span class="sxs-lookup"><span data-stu-id="dc5ad-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="dc5ad-125">Чтобы включить анонимный доступ пользователей, установите для свойства **AllowAnonymousUsers** значение True ($True):</span><span class="sxs-lookup"><span data-stu-id="dc5ad-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="dc5ad-126">Отключение анонимного доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="dc5ad-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="dc5ad-127">Чтобы отключить анонимный доступ пользователей, установите для свойства **AllowAnonymousUsers** значение False ($False):</span><span class="sxs-lookup"><span data-stu-id="dc5ad-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="dc5ad-128">См. также</span><span class="sxs-lookup"><span data-stu-id="dc5ad-128">See Also</span></span>

[<span data-ttu-id="dc5ad-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="dc5ad-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
