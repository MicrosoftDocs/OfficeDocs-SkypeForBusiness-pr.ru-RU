---
title: Enable users for Корпоративная голосовая связь in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: Сводка. Узнайте, как позволить пользователям делать и принимать звонки с помощью Корпоративная голосовая связь в Skype для бизнеса Server.
ms.openlocfilehash: 3c18836f1c2b03d2c6d50712f33d9e3a900b43b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830879"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="f39c1-103">Enable users for Корпоративная голосовая связь in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f39c1-103">Enable users for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="f39c1-104">**Сводка:** Узнайте, как позволить пользователям делать и принимать звонки с помощью Корпоративная голосовая связь Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f39c1-104">**Summary:** Learn how to enable users to make and receive calls by using Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="f39c1-105">После развертывания Корпоративная голосовая связь или вызова с помощью работы можно использовать следующие процедуры, чтобы позволить пользователю звонить с помощью Корпоративная голосовая связь:</span><span class="sxs-lookup"><span data-stu-id="f39c1-105">After you deploy Enterprise Voice or Call Via Work, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>
  
> [!NOTE]
> <span data-ttu-id="f39c1-106">Из следующих процедур с помощью панели управления Skype для бизнеса Server можно выполнить только первую из них.</span><span class="sxs-lookup"><span data-stu-id="f39c1-106">Of the following procedures, only the first can be performed by using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="f39c1-107">Для остальных процедур можно использовать только оболочку управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f39c1-107">For the remaining procedures, you can use only Skype for Business Server Management Shell.</span></span> 
  
- <span data-ttu-id="f39c1-108">В этой учетной записи пользователя Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="f39c1-108">Enable the user account for Enterprise Voice.</span></span>
    
- <span data-ttu-id="f39c1-109">(Необязательно) Назначьте учетной записи пользователя определенную политику голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="f39c1-109">(Optional) Assign the user account a user-specific voice policy.</span></span>
    
- <span data-ttu-id="f39c1-110">(Необязательно) Назначьте учетной записи пользователя определенную абонентскую группу.</span><span class="sxs-lookup"><span data-stu-id="f39c1-110">(Optional) Assign the user account a user-specific dial plan.</span></span>
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="f39c1-111">Чтобы включить учетную запись пользователя для Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="f39c1-111">To enable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="f39c1-112">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="f39c1-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="f39c1-113">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="f39c1-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f39c1-114">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="f39c1-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="f39c1-115">В поле **Поиск пользователей** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (диспетчера учетных записей безопасности), SIP-адрес или линейный универсальный код ресурса (URI) учетной записи пользователя, которой требуется разрешить корпоративную голосовую связи, а затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="f39c1-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="f39c1-116">В таблице щелкните учетную запись пользователя, которую необходимо включить для Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="f39c1-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="f39c1-117">В меню **Edit** (Правка) щелкните пункт  **Show details** (Показать подробности).</span><span class="sxs-lookup"><span data-stu-id="f39c1-117">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="f39c1-118">On the **Edit Skype for Business Server User** page, under **Telephony,** click **Корпоративная голосовая связь**.</span><span class="sxs-lookup"><span data-stu-id="f39c1-118">On the **Edit Skype for Business Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="f39c1-119">Щелкните **Строковый URI** и введите уникальный нормализованный номер телефона (например, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="f39c1-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
9. <span data-ttu-id="f39c1-120">Щелкните **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="f39c1-120">Click **Commit**.</span></span>
    
<span data-ttu-id="f39c1-121">Чтобы завершить включение пользователя для Корпоративная голосовая связь, убедитесь, что пользователю назначена политика голосовой почты и телефонная плана, глобальная (назначенная по умолчанию) или пользователь. По умолчанию всем пользователям назначена глобальная политика голосовой почты и телефонная плана.</span><span class="sxs-lookup"><span data-stu-id="f39c1-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="f39c1-122">Если голосовая политика или абонентская группа существуют на уровне сайта для того сайта, на котором размещена учетная запись пользователя, эта политика будет автоматически применена к пользователю.</span><span class="sxs-lookup"><span data-stu-id="f39c1-122">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="f39c1-123">Чтобы применить голосовую политику или абонентскую группу на уровне пользователя к определенному пользователю, необходимо выполнить командлеты **Grant-CsVoicePolicy** и **Grant-CsDialPlan**.</span><span class="sxs-lookup"><span data-stu-id="f39c1-123">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="f39c1-124">Подробные сведения см. в следующих процедурах в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="f39c1-124">For details, see the following procedures in this topic.</span></span>
## <a name="voice-policy-assignment"></a><span data-ttu-id="f39c1-125">Назначение политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="f39c1-125">Voice Policy Assignment</span></span>

<span data-ttu-id="f39c1-126">Глобальные политики голосовой почты и политики голосовой почты на уровне сайта автоматически назначены всем учетным записям пользователей, для Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="f39c1-126">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="f39c1-127">Вы также можете создать политики, которые применяются к определенным пользователям или группам.</span><span class="sxs-lookup"><span data-stu-id="f39c1-127">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="f39c1-128">Их необходимо назначить явно.</span><span class="sxs-lookup"><span data-stu-id="f39c1-128">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="f39c1-129">Если вы хотите использовать глобальную политику или политику голосовой связи сайта для всех пользователей, [](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) для которых включена Корпоративная голосовая связь, можно пропустить этот раздел и перейти к разделу "Назначение телефонной плана" далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="f39c1-129">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to [Dial Plan Assignment](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) section later in this topic.</span></span>
  
### <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="f39c1-130">Назначение политики голосовой связи для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="f39c1-130">To assign a user-specific voice policy</span></span>

1. <span data-ttu-id="f39c1-131">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f39c1-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f39c1-132">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="f39c1-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f39c1-133">Чтобы назначить существующую политику голосовой связи пользователю, выполните следующую команду в окне командной строки:</span><span class="sxs-lookup"><span data-stu-id="f39c1-133">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="f39c1-134">Пример:</span><span class="sxs-lookup"><span data-stu-id="f39c1-134">For example:</span></span>
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    <span data-ttu-id="f39c1-135">В этом примере пользователю с отображаемым именем Bob Kelly назначена политика голосовой связи с именем **VoicePolicyJapan.**</span><span class="sxs-lookup"><span data-stu-id="f39c1-135">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>
    
## <a name="dial-plan-assignment"></a><span data-ttu-id="f39c1-136">Назначение абонентской группы</span><span class="sxs-lookup"><span data-stu-id="f39c1-136">Dial Plan Assignment</span></span>
<span data-ttu-id="f39c1-137"><a name="BKMK_DialPlanAssignment"> </a></span><span class="sxs-lookup"><span data-stu-id="f39c1-137"><a name="BKMK_DialPlanAssignment"> </a></span></span>

<span data-ttu-id="f39c1-138">Чтобы выполнить настройку учетной записи пользователя как для пользователей корпоративной голосовой связи, так и для пользователей конференц-связи с телефонным подключением, этот пользователь должен быть назначен соответствующей абонентской группе.</span><span class="sxs-lookup"><span data-stu-id="f39c1-138">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="f39c1-139">Учетные записи пользователей будут автоматически применять глобальную абонентскую группу или, если такая имеется, абонентскую группу на уровне сайта, если вы явно не назначите абонентскую группу для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="f39c1-139">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="f39c1-140">Если вы хотите использовать глобальную или на уровне сайта для всех пользователей, для которых включена Корпоративная голосовая связь, этот раздел можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="f39c1-140">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>
  
### <a name="to-assign-a-user-specific-dial-plan"></a><span data-ttu-id="f39c1-141">Назначение определенной пользователем телефонной программы</span><span class="sxs-lookup"><span data-stu-id="f39c1-141">To assign a user-specific dial plan</span></span>

1. <span data-ttu-id="f39c1-142">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f39c1-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f39c1-143">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="f39c1-143">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f39c1-144">Чтобы назначить абонентскую группу для отдельных пользователей, выполните следующую команду в окне командной строки:</span><span class="sxs-lookup"><span data-stu-id="f39c1-144">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="f39c1-145">Пример:</span><span class="sxs-lookup"><span data-stu-id="f39c1-145">For example:</span></span>
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    <span data-ttu-id="f39c1-146">В этом примере пользователю с отображаемой именем Bob Kelly назначена пользователь с именем **DialPlanJapan.**</span><span class="sxs-lookup"><span data-stu-id="f39c1-146">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>
    

