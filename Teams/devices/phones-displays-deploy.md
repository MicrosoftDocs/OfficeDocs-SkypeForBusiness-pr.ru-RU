---
title: Развертывание Teams телефонов и Teams с помощью Intune
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: В этой статье дается обзор функций, поддерживаемых Microsoft Teams дисплеев.
ms.openlocfilehash: ee5b536aaadaf458b6edf9b32dea299a3ecad9a0
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420824"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="c8f14-103">Развертывание Teams телефонов и Teams с помощью Intune</span><span class="sxs-lookup"><span data-stu-id="c8f14-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="c8f14-104">В этой статье представлен обзор развертывания.</span><span class="sxs-lookup"><span data-stu-id="c8f14-104">This article gives you an overview of how to deploy.</span></span> <span data-ttu-id="c8f14-105">Teams и Teams с помощью Intune.</span><span class="sxs-lookup"><span data-stu-id="c8f14-105">Teams phones and Teams display using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="c8f14-106">Условный доступ</span><span class="sxs-lookup"><span data-stu-id="c8f14-106">Conditional Access</span></span>

<span data-ttu-id="c8f14-107">Условный доступ — это Azure Active Directory (Azure AD), которая помогает обеспечить правильное управление ресурсами Office 365 устройствами и безопасностью.</span><span class="sxs-lookup"><span data-stu-id="c8f14-107">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="c8f14-108">Если вы применяли политики условного доступа к службе Teams, устройства с Android (включая телефоны Teams и экраны Teams), которые имеют доступ к Teams, должны быть зарегистрированы в Intune, а их параметры должны соответствовать вашим политикам.</span><span class="sxs-lookup"><span data-stu-id="c8f14-108">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams needs to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="c8f14-109">Если устройство не зарегистрировать в Intune или зарегистрировать его, но его параметры не соответствуют вашим политикам, Условный доступ не позволит пользователю войди в приложение Teams на устройстве.</span><span class="sxs-lookup"><span data-stu-id="c8f14-109">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="c8f14-110">Как правило, политики соответствия требованиям, определенные в Intune, назначены группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="c8f14-110">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="c8f14-111">Это означает, что если назначить политику соответствия user@contoso.com Android, она будет в равной степени применяться к смартфону с Android и к любому устройству с Android Teams на которое user@contoso.com устройства.</span><span class="sxs-lookup"><span data-stu-id="c8f14-111">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="c8f14-112">Если вы используете условный доступ, который требует принудительного регистрации Intune, в вашей организации необходимо настроить несколько условий, позволяющих успешно зарегистрироваться в Intune:</span><span class="sxs-lookup"><span data-stu-id="c8f14-112">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="c8f14-113">**Лицензия intune** Пользователь, во который Teams устройство, должен иметь лицензию на Intune.</span><span class="sxs-lookup"><span data-stu-id="c8f14-113">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="c8f14-114">Если устройство Teams в учетную запись пользователя с действующей лицензией Intune, оно будет автоматически зарегистрироваться в Microsoft Intune в процессе регистрации.</span><span class="sxs-lookup"><span data-stu-id="c8f14-114">As long as the Teams device is signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="c8f14-115">**Настройка Intune** Для регистрации администратора устройств с Android необходимо правильно настроить клиент Intune.</span><span class="sxs-lookup"><span data-stu-id="c8f14-115">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="c8f14-116">Настройка Intune для регистрации Teams устройств на базе Android</span><span class="sxs-lookup"><span data-stu-id="c8f14-116">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="c8f14-117">Teams Устройства на базе Android управляются Intune с помощью управления устройствами с Android (DA).</span><span class="sxs-lookup"><span data-stu-id="c8f14-117">Teams Android-based devices are managed by Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="c8f14-118">Перед регистрацией устройств в Intune необходимо выполнить несколько основных действий.</span><span class="sxs-lookup"><span data-stu-id="c8f14-118">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="c8f14-119">Если вы уже управляете устройствами в Intune сегодня, вероятно, вы уже сделали все это.</span><span class="sxs-lookup"><span data-stu-id="c8f14-119">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="c8f14-120">Если нет, вот что нужно сделать:</span><span class="sxs-lookup"><span data-stu-id="c8f14-120">If not, here’s what to do:</span></span>

> [!NOTE]
> - <span data-ttu-id="c8f14-121">Если администраторы клиентов хотят, чтобы в Intune были зарегистрированы обычные телефоны с районами, им необходимо добавить в учетную запись лицензию Intune и следуйте этим шагам.</span><span class="sxs-lookup"><span data-stu-id="c8f14-121">If tenant admins want common area phones to be enrolled into Intune, they need to add an Intune license to the account and follow the steps for Intune enrollment.</span></span>
> - <span data-ttu-id="c8f14-122">Если учетная запись пользователя, используемая для Teams устройства, не лицензирована на Intune, политики соответствия требованиям и ограничения регистрации Intune необходимо отключить для этой учетной записи.</span><span class="sxs-lookup"><span data-stu-id="c8f14-122">If the user account used to sign into a Teams device isn't licensed for Intune, Intune compliance policies and enrollment restrictions need to be disabled for the account.</span></span>



1. <span data-ttu-id="c8f14-123">Установите для Intune MDM (управление мобильными устройствами) полномочия.</span><span class="sxs-lookup"><span data-stu-id="c8f14-123">Set Intune MDM (mobile device management) Authority.</span></span>  

   <span data-ttu-id="c8f14-124">Если вы никогда не использовали Intune, для регистрации устройств необходимо настроить полномочия MDM.</span><span class="sxs-lookup"><span data-stu-id="c8f14-124">If you’ve never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="c8f14-125">Дополнительные сведения см. в руководстве по [управлению мобильными устройствами.](/intune/fundamentals/mdm-authority-set)</span><span class="sxs-lookup"><span data-stu-id="c8f14-125">For more information, see [Set the mobile device management authority](/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="c8f14-126">Это разовые этапы, которые необходимо сделать при создании нового клиента Intune.</span><span class="sxs-lookup"><span data-stu-id="c8f14-126">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
1. <span data-ttu-id="c8f14-127">Включить регистрацию администратора устройств с Android.</span><span class="sxs-lookup"><span data-stu-id="c8f14-127">Enable Android device administrator enrollment.</span></span>
  
   <span data-ttu-id="c8f14-128">Устройствами Teams Android управляется как устройства администратора устройств с помощью Intune.</span><span class="sxs-lookup"><span data-stu-id="c8f14-128">Android-based Teams devices are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="c8f14-129">Регистрация администратора устройства по умолчанию отключена для новых клиентов.</span><span class="sxs-lookup"><span data-stu-id="c8f14-129">Device administrator enrollment is off by default for newly created tenants.</span></span> <span data-ttu-id="c8f14-130">См. [регистрацию администратора устройств с Android.](/intune/enrollment/android-enroll-device-administrator)</span><span class="sxs-lookup"><span data-stu-id="c8f14-130">See [Android device administrator enrollment](/intune/enrollment/android-enroll-device-administrator).</span></span>
1. <span data-ttu-id="c8f14-131">Назначение лицензий пользователям.</span><span class="sxs-lookup"><span data-stu-id="c8f14-131">Assign licenses to users.</span></span> 
 
   <span data-ttu-id="c8f14-132">Пользователям Teams устройств, зарегистрированных в Intune, должна быть назначена действительная лицензия intune.</span><span class="sxs-lookup"><span data-stu-id="c8f14-132">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="c8f14-133">Дополнительные сведения см. в статьи Назначение лицензий пользователям для регистрации [устройств в Intune.](/intune/fundamentals/licenses-assign)</span><span class="sxs-lookup"><span data-stu-id="c8f14-133">For more information, see [Assign licenses to users so they can enroll devices in Intune](/intune/fundamentals/licenses-assign).</span></span>
1. <span data-ttu-id="c8f14-134">Назначьте политики соответствия администраторам устройств.</span><span class="sxs-lookup"><span data-stu-id="c8f14-134">Assign Device Administrator compliance policies.</span></span>  

   <span data-ttu-id="c8f14-135">а)</span><span class="sxs-lookup"><span data-stu-id="c8f14-135">a.</span></span> <span data-ttu-id="c8f14-136">Создайте политику соответствия администратора устройств Android.</span><span class="sxs-lookup"><span data-stu-id="c8f14-136">Create an Android Device Administrator compliance policy.</span></span>

   <span data-ttu-id="c8f14-137">б)</span><span class="sxs-lookup"><span data-stu-id="c8f14-137">b.</span></span> <span data-ttu-id="c8f14-138">Назначьте его группе Azure Active Directory, которая содержит пользователей, которые будут в нее в Teams устройств.</span><span class="sxs-lookup"><span data-stu-id="c8f14-138">Assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="c8f14-139">См. [использование политик соответствия для набора правил для устройств, управляемых с помощью Intune.](/mem/intune/protect/device-compliance-get-started)</span><span class="sxs-lookup"><span data-stu-id="c8f14-139">See [Use compliance policies to set rules for devices you manage with Intune](/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="c8f14-140">См. также</span><span class="sxs-lookup"><span data-stu-id="c8f14-140">See also</span></span>

[<span data-ttu-id="c8f14-141">Телефоны для Teams</span><span class="sxs-lookup"><span data-stu-id="c8f14-141">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="c8f14-142">IP-телефоны, сертифицированные для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c8f14-142">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="c8f14-143">Teams отображает</span><span class="sxs-lookup"><span data-stu-id="c8f14-143">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="c8f14-144">Управление устройствами в Teams</span><span class="sxs-lookup"><span data-stu-id="c8f14-144">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="c8f14-145">Teams Рынке</span><span class="sxs-lookup"><span data-stu-id="c8f14-145">Teams Marketplace</span></span>](https://office.com/teamsdevices)