---
title: Включение пользователей для корпоративной голосовой связи в Скайп для Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Сводка: Узнайте, как разрешить пользователям выполнение и прием звонков с помощью корпоративной голосовой связи в Скайп for Business Server.'
ms.openlocfilehash: 9e1435c73a175ef40b4962ace41f4c7690f85953
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883758"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="54b23-103">Включение пользователей для корпоративной голосовой связи в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="54b23-103">Enable users for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="54b23-104">**Сводка:** Узнайте, как разрешить пользователям выполнение и прием звонков с помощью корпоративной голосовой связи в Скайп for Business Server.</span><span class="sxs-lookup"><span data-stu-id="54b23-104">**Summary:** Learn how to enable users to make and receive calls by using Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="54b23-105">После развертывания корпоративной голосовой связи или звонок с помощью работа для разрешения пользователю выполнять вызовы с помощью корпоративной голосовой связи можно использовать следующие процедуры:</span><span class="sxs-lookup"><span data-stu-id="54b23-105">After you deploy Enterprise Voice or Call Via Work, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>
  
> [!NOTE]
> <span data-ttu-id="54b23-106">Из приведенных ниже только первые могут выполняться с помощью Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="54b23-106">Of the following procedures, only the first can be performed by using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="54b23-107">Для остальных процедур можно использовать только Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="54b23-107">For the remaining procedures, you can use only Skype for Business Server Management Shell.</span></span> 
  
- <span data-ttu-id="54b23-108">Включение учетной записи пользователя для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="54b23-108">Enable the user account for Enterprise Voice.</span></span>
    
- <span data-ttu-id="54b23-109">(Необязательно) Назначьте учетной записи пользователя определенную политику голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="54b23-109">(Optional) Assign the user account a user-specific voice policy.</span></span>
    
- <span data-ttu-id="54b23-110">(Необязательно) Назначьте учетной записи пользователя определенную абонентскую группу.</span><span class="sxs-lookup"><span data-stu-id="54b23-110">(Optional) Assign the user account a user-specific dial plan.</span></span>
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="54b23-111">Включение учетной записи пользователя для корпоративной голосовой связи</span><span class="sxs-lookup"><span data-stu-id="54b23-111">To enable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="54b23-112">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="54b23-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="54b23-113">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="54b23-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="54b23-114">На панели навигации слева щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="54b23-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="54b23-115">В поле **Поиск пользователей** введите отображаемое имя или его начальный фрагмент, имя, фамилию, имя учетной записи (диспетчера учетных записей безопасности (SAM), SIP-адрес или строку универсального кода ресурса (URI) из учетной записи пользователя, которому требуется предоставить доступ, затем нажмите кнопку **Найти**.</span><span class="sxs-lookup"><span data-stu-id="54b23-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="54b23-116">В таблице щелкните учетную запись пользователя, необходимо включить для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="54b23-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="54b23-117">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="54b23-117">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="54b23-118">На странице " **Изменение Скайп для пользователя Business Server** " в разделе **Телефония**щелкните **Enterprise Voice**.</span><span class="sxs-lookup"><span data-stu-id="54b23-118">On the **Edit Skype for Business Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="54b23-119">Щелкните **URI строки** и введите уникальный нормализованный номер телефона (например, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="54b23-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
9. <span data-ttu-id="54b23-120">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="54b23-120">Click **Commit**.</span></span>
    
<span data-ttu-id="54b23-121">Чтобы закончить Включение пользователю Enterprise Voice, убедитесь, что пользователю назначена политика голосовой связи и абонентской группы, глобальная (назначается по умолчанию) или пользовательская. По умолчанию всем пользователям назначена политика глобального голосовой связи и абонентская группа.</span><span class="sxs-lookup"><span data-stu-id="54b23-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="54b23-122">Если голосовой политики или телефонным плана на уровне сайта для сайта, на котором размещен учетная запись пользователя, эти политики сайта автоматически применяется к пользователю.</span><span class="sxs-lookup"><span data-stu-id="54b23-122">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="54b23-123">Для применения политики голосовой связи уровня пользователя или абонентская группа для пользователей, необходимо выполнить командлеты **Grant-CsVoicePolicy** и **Grant-CsDialPlan** .</span><span class="sxs-lookup"><span data-stu-id="54b23-123">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="54b23-124">Сведения о них см.</span><span class="sxs-lookup"><span data-stu-id="54b23-124">For details, see the following procedures in this topic.</span></span>
## <a name="voice-policy-assignment"></a><span data-ttu-id="54b23-125">Назначение политики голосовой связи</span><span class="sxs-lookup"><span data-stu-id="54b23-125">Voice Policy Assignment</span></span>

<span data-ttu-id="54b23-126">Политики голосовой связи глобальном уровне и на уровне сайтов автоматически назначаются все учетные записи пользователей, которые включены для корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="54b23-126">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="54b23-127">Можно также создавать политики, применимые к определенным пользователям или группам.</span><span class="sxs-lookup"><span data-stu-id="54b23-127">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="54b23-128">Такие политики необходимо назначать пользователям или группам в явном виде.</span><span class="sxs-lookup"><span data-stu-id="54b23-128">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="54b23-129">Если вы хотите использовать глобальный или веб-сайтов политика голосовой связи для всех пользователей, которым разрешена Корпоративная голосовая связь, можно пропустить этот раздел и перейдите к [Телефонным Планирование назначения](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) данной статьи данного раздела.</span><span class="sxs-lookup"><span data-stu-id="54b23-129">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to [Dial Plan Assignment](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) section later in this topic.</span></span>
  
### <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="54b23-130">Назначение политики голосовой связи для отдельных пользователей</span><span class="sxs-lookup"><span data-stu-id="54b23-130">To assign a user-specific voice policy</span></span>

1. <span data-ttu-id="54b23-131">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="54b23-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="54b23-132">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="54b23-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="54b23-133">Чтобы назначить существующую политику голосовой связи пользователю, выполните следующую команду в окне командной строки:</span><span class="sxs-lookup"><span data-stu-id="54b23-133">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="54b23-134">Например:</span><span class="sxs-lookup"><span data-stu-id="54b23-134">For example:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    <span data-ttu-id="54b23-135">В этом примере пользователю с отображаемым именем Bob Kelly назначается политика голосовой связи с именем **VoicePolicyJapan**.</span><span class="sxs-lookup"><span data-stu-id="54b23-135">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>
    
## <a name="dial-plan-assignment"></a><span data-ttu-id="54b23-136">Назначение абонентской группы</span><span class="sxs-lookup"><span data-stu-id="54b23-136">Dial Plan Assignment</span></span>
<span data-ttu-id="54b23-137"><a name="BKMK_DialPlanAssignment"> </a></span><span class="sxs-lookup"><span data-stu-id="54b23-137"></span></span>

<span data-ttu-id="54b23-138">Для завершения настройки учетной записи пользователя для пользователей корпоративной голосовой связи или пользователи конференц-связи, пользователь должен быть назначен в абонентской группе.</span><span class="sxs-lookup"><span data-stu-id="54b23-138">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="54b23-139">Учетные записи пользователей автоматически будет использовать глобальные абонентской или, если таковой имеется уровня сайта абонентской при явно не присвоить существующую абонентскую группу на пользователя.</span><span class="sxs-lookup"><span data-stu-id="54b23-139">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="54b23-140">Если вы хотите использовать глобальный или веб-сайтов абонентской группы для всех пользователей, которым разрешена Корпоративная голосовая связь, можно пропустить этот раздел.</span><span class="sxs-lookup"><span data-stu-id="54b23-140">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>
  
### <a name="to-assign-a-user-specific-dial-plan"></a><span data-ttu-id="54b23-141">Назначение абонентской группы уровня пользователя</span><span class="sxs-lookup"><span data-stu-id="54b23-141">To assign a user-specific dial plan</span></span>

1. <span data-ttu-id="54b23-142">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="54b23-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="54b23-143">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="54b23-143">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="54b23-144">Чтобы назначить абонентскую группу для отдельных пользователей, выполните следующую команду в окне командной строки:</span><span class="sxs-lookup"><span data-stu-id="54b23-144">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="54b23-145">Например:</span><span class="sxs-lookup"><span data-stu-id="54b23-145">For example:</span></span>
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    <span data-ttu-id="54b23-146">В этом примере пользователю с отображаемым именем Bob Kelly назначается абонентская **Группа dialplanjapan**.</span><span class="sxs-lookup"><span data-stu-id="54b23-146">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>
    

