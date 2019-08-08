---
title: Включение пользователей корпоративной голосовой связи в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Сводка: сведения о том, как разрешить пользователям совершать и принимать звонки с помощью корпоративной голосовой связи в Skype для бизнеса Server.'
ms.openlocfilehash: cf9aab0f104582c57e745c95ae5cf8f24f07b3a5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240333"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="ea32e-103">Включение пользователей корпоративной голосовой связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ea32e-103">Enable users for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="ea32e-104">**Сводка:** Сведения о том, как разрешить пользователям совершать и принимать звонки с помощью корпоративной голосовой связи в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ea32e-104">**Summary:** Learn how to enable users to make and receive calls by using Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="ea32e-105">После развертывания корпоративной голосовой или телефонной связи через Work вы можете использовать следующие процедуры, чтобы разрешить пользователю звонить с помощью корпоративной голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="ea32e-105">After you deploy Enterprise Voice or Call Via Work, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>
  
> [!NOTE]
> <span data-ttu-id="ea32e-106">Из описанных ниже процедур можно выполнить только первую операцию с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ea32e-106">Of the following procedures, only the first can be performed by using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="ea32e-107">Для остальных процедур вы можете использовать только командную консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ea32e-107">For the remaining procedures, you can use only Skype for Business Server Management Shell.</span></span> 
  
- <span data-ttu-id="ea32e-108">Включение учетной записи пользователя для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="ea32e-108">Enable the user account for Enterprise Voice.</span></span>
    
- <span data-ttu-id="ea32e-109">(Необязательно) Назначьте учетной записи пользователя определенную политику голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="ea32e-109">(Optional) Assign the user account a user-specific voice policy.</span></span>
    
- <span data-ttu-id="ea32e-110">(Необязательно) Назначьте учетной записи пользователя определенную абонентскую группу.</span><span class="sxs-lookup"><span data-stu-id="ea32e-110">(Optional) Assign the user account a user-specific dial plan.</span></span>
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="ea32e-111">Включение учетной записи пользователя для корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="ea32e-111">To enable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="ea32e-112">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="ea32e-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="ea32e-113">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ea32e-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ea32e-114">На левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="ea32e-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="ea32e-115">В поле **Поиск пользователей** введите отображаемое имя или его начальный фрагмент, имя, фамилию, имя учетной записи (диспетчера учетных записей безопасности (SAM), SIP-адрес или строку универсального кода ресурса (URI) из учетной записи пользователя, которому требуется предоставить доступ, затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="ea32e-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="ea32e-116">В таблице выберите учетную запись пользователя, которую вы хотите включить для корпоративного голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="ea32e-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="ea32e-117">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="ea32e-117">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="ea32e-118">На странице " **изменение пользователя Skype для бизнеса Server** " в разделе **телефония**выберите **Корпоративный голосовой звонок**.</span><span class="sxs-lookup"><span data-stu-id="ea32e-118">On the **Edit Skype for Business Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="ea32e-119">Щелкните **URI строки** и введите уникальный нормализованный номер телефона (например, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="ea32e-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
9. <span data-ttu-id="ea32e-120">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="ea32e-120">Click **Commit**.</span></span>
    
<span data-ttu-id="ea32e-121">Чтобы завершить включение пользователя для корпоративного голосовой связи, убедитесь, что пользователю назначена политика голосовой связи и абонентская группа, будь это глобальная (назначена по умолчанию) или для определенного пользователя. По умолчанию всем пользователям назначается Глобальная политика голосовой связи и абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="ea32e-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="ea32e-122">Если политика голосовой связи или абонентские группы находятся на уровне сайта для сайта, на котором находится учетная запись пользователя, эти политики сайта будут автоматически применены к пользователю.</span><span class="sxs-lookup"><span data-stu-id="ea32e-122">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="ea32e-123">Чтобы применить политику голосовой почты или абонентскую группу для пользователя, необходимо запустить командлеты **Grant-ксвоицеполици** и **Grant-ксдиалплан** .</span><span class="sxs-lookup"><span data-stu-id="ea32e-123">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="ea32e-124">Дополнительные сведения можно найти в описанных ниже процедурах.</span><span class="sxs-lookup"><span data-stu-id="ea32e-124">For details, see the following procedures in this topic.</span></span>
## <a name="voice-policy-assignment"></a><span data-ttu-id="ea32e-125">Назначение политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="ea32e-125">Voice Policy Assignment</span></span>

<span data-ttu-id="ea32e-126">Глобальные политики и стратегии голосовой связи на уровне сайта автоматически назначаются всем учетным записям пользователей, которые включены в корпоративный голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="ea32e-126">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="ea32e-127">Можно также создавать политики, применимые к определенным пользователям или группам.</span><span class="sxs-lookup"><span data-stu-id="ea32e-127">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="ea32e-128">Такие политики необходимо назначать пользователям или группам в явном виде.</span><span class="sxs-lookup"><span data-stu-id="ea32e-128">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="ea32e-129">Если вы хотите использовать глобальную политику голосовой почты для всех пользователей, которым разрешена Корпоративная голосовая связь, вы можете пропустить этот раздел и перейти к разделу [назначение абонентской группы](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) ниже в этой статье.</span><span class="sxs-lookup"><span data-stu-id="ea32e-129">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to [Dial Plan Assignment](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) section later in this topic.</span></span>
  
### <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="ea32e-130">Назначение политики голосовой связи для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="ea32e-130">To assign a user-specific voice policy</span></span>

1. <span data-ttu-id="ea32e-131">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ea32e-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ea32e-132">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="ea32e-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ea32e-133">Чтобы назначить существующую политику голосовой связи пользователю, выполните следующую команду в окне командной строки:</span><span class="sxs-lookup"><span data-stu-id="ea32e-133">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="ea32e-134">Например:</span><span class="sxs-lookup"><span data-stu-id="ea32e-134">For example:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    <span data-ttu-id="ea32e-135">В этом примере пользователь с отображаемым именем Bob Юлия назначается политике голосовой связи с именем **воицеполицижапан**.</span><span class="sxs-lookup"><span data-stu-id="ea32e-135">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>
    
## <a name="dial-plan-assignment"></a><span data-ttu-id="ea32e-136">Назначение абонентской группы</span><span class="sxs-lookup"><span data-stu-id="ea32e-136">Dial Plan Assignment</span></span>
<span data-ttu-id="ea32e-137"><a name="BKMK_DialPlanAssignment"> </a></span><span class="sxs-lookup"><span data-stu-id="ea32e-137"></span></span>

<span data-ttu-id="ea32e-138">Чтобы завершить настройку учетной записи пользователя либо для пользователей корпоративной голосовой связи, либо для пользователей конференц-связи с телефонным подключением, пользователю должна быть назначена абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="ea32e-138">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="ea32e-139">Учетные записи пользователей будут автоматически использовать глобальную абонентскую группу или, если таковая существует, это абонентская группа на уровне сайта, если вы не хотите явно назначать существующий абонентский набор для пользователей.</span><span class="sxs-lookup"><span data-stu-id="ea32e-139">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="ea32e-140">Если вы хотите использовать глобальную или общую абонентскую группу для всех пользователей, для которых разрешена Корпоративная голосовая связь, вы можете пропустить этот раздел.</span><span class="sxs-lookup"><span data-stu-id="ea32e-140">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>
  
### <a name="to-assign-a-user-specific-dial-plan"></a><span data-ttu-id="ea32e-141">Назначение абонентской группы уровня пользователя</span><span class="sxs-lookup"><span data-stu-id="ea32e-141">To assign a user-specific dial plan</span></span>

1. <span data-ttu-id="ea32e-142">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ea32e-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ea32e-143">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="ea32e-143">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ea32e-144">Чтобы назначить абонентскую группу для отдельных пользователей, выполните следующую команду в окне командной строки:</span><span class="sxs-lookup"><span data-stu-id="ea32e-144">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="ea32e-145">Например:</span><span class="sxs-lookup"><span data-stu-id="ea32e-145">For example:</span></span>
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    <span data-ttu-id="ea32e-146">В этом примере пользователю с отображаемым именем Bob Юлия назначается абонентская группа с именем **диалпланжапан**.</span><span class="sxs-lookup"><span data-stu-id="ea32e-146">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>
    

