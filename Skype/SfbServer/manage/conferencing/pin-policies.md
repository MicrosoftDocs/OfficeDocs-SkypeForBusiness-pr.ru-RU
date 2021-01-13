---
title: Manage PIN policies for dial-in conferencing in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: Сводка. Узнайте, как управлять политиками ПИН-кодов для телефонной сети в Skype для бизнеса Server.
ms.openlocfilehash: 6544586071f1107537232a117de196dfbffeb4aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827959"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="835a4-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="835a4-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="835a4-104">**Сводка:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="835a4-104">**Summary:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="835a4-105">Пользователи Skype для бизнеса Server с учетными данными доменных служб Active Directory (AD DS) в вашей организации могут присоединяться к конференциям с телефонным доступом в качестве пользователей, подлинность которых прошла проверку подлинности, с помощью персонального идентификационных номеров (ПИН-кода).</span><span class="sxs-lookup"><span data-stu-id="835a4-105">Skype for Business Server users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="835a4-106">Политика ПИН-кодов определяет способ работы ПИН-кодов для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="835a4-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>
  
 <span data-ttu-id="835a4-107">Если вы хотите применить одну и ту же политику ПИН-кодов ко всей организации, вы можете использовать глобальную политику ПИН-кодов, изменив ее так, как нужно.</span><span class="sxs-lookup"><span data-stu-id="835a4-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="835a4-108">Глобальная политика ПИН-кодов определяет правила для ПИН-кодов конференц-связи с телефонным подключением на уровне лесов.</span><span class="sxs-lookup"><span data-stu-id="835a4-108">The global PIN policy defines the rules for dial-in conferencing PINs at the forest level.</span></span> <span data-ttu-id="835a4-109">Вы можете изменить глобальную политику ПИН-кодов, но не можете удалить ее.</span><span class="sxs-lookup"><span data-stu-id="835a4-109">You can modify the global PIN policy, but you cannot delete it.</span></span>
  
<span data-ttu-id="835a4-110">Чтобы применить особую политику к узлу или группе пользователей, вы можете создать новую политику ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="835a4-110">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span>
  
<span data-ttu-id="835a4-111">Политики ПИН-кодов применяются к пользователям в очередности от самой узкой области действия до самой широкой.</span><span class="sxs-lookup"><span data-stu-id="835a4-111">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="835a4-112">Если вы назначили пользователю политику ПИН-кодов на уровне пользователя, ее параметры имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="835a4-112">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="835a4-113">Если вы не назначили политику пользователя, применяется политика ПИН-кодов на уровне узла, если она определена.</span><span class="sxs-lookup"><span data-stu-id="835a4-113">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="835a4-114">Если политики пользователя и узла не назначены, действуют параметры по умолчанию глобальной политики ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="835a4-114">If no user or site policies apply, global PIN policy provides the default settings.</span></span>
  
## <a name="view-information-about-pin-policies"></a><span data-ttu-id="835a4-115">Просмотр сведений о политиках ПИН-кодов</span><span class="sxs-lookup"><span data-stu-id="835a4-115">View information about PIN policies</span></span>

<span data-ttu-id="835a4-116">Сведения о политиках ПИН-кодов можно просмотреть с помощью панели управления Skype для бизнеса Server или с помощью skype для бизнеса Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="835a4-116">You can view information about PIN policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="835a4-117">Просмотр сведений о политиках ПИН-кодов с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="835a4-117">View information about PIN policies by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="835a4-118">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или которой назначена роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="835a4-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="835a4-119">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="835a4-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="835a4-120">В левой панели навигации щелкните элемент **Conferencing** (Конференц-связь), а затем щелкните элемент **PIN Policy** (Политика ПИН-кодов).</span><span class="sxs-lookup"><span data-stu-id="835a4-120">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="835a4-121">На странице **"Политика ПИН-кодов"** щелкните политику ПИН-кодов, которую необходимо просмотреть, нажмите кнопку "Изменить" и выберите **"Показать подробности".**</span><span class="sxs-lookup"><span data-stu-id="835a4-121">On the **PIN Policy** page, click the PIN policy that you want to view, click **Edit**, and then click **Show details**.</span></span>
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="835a4-122">Просмотр сведений о политиках ПИН-кодов с помощью оболочки управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="835a4-122">View information about PIN policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="835a4-123">Чтобы просмотреть сведения о политиках ПИН-кодов, используйте **cmdlet Get-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="835a4-123">To view information about PIN policies, use the **Get-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="835a4-124">Например, следующая команда возвращает сведения об одной политике ПИН-кодов с идентификатором site:Redmond:</span><span class="sxs-lookup"><span data-stu-id="835a4-124">For example, the following command returns information about a single PIN policy with the Identity site:Redmond:</span></span>
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

<span data-ttu-id="835a4-125">Дополнительные сведения, включая полное описание синтаксиса и список параметров, см. в описании [get-CsPinPolicy.](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="835a4-125">For more information, including a complete syntax description and list of parameters, see [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-the-global-pin-policy"></a><span data-ttu-id="835a4-126">Изменение глобальной политики ПИН-кодов</span><span class="sxs-lookup"><span data-stu-id="835a4-126">Modify the global PIN policy</span></span>

<span data-ttu-id="835a4-127">Глобальную политику ПИН-кодов можно изменить с помощью панели управления Skype для бизнеса Server или с помощью skype для бизнеса Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="835a4-127">You can modify the global PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="835a4-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="835a4-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="835a4-129">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или которой назначена роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="835a4-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="835a4-130">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="835a4-130">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="835a4-131">В левой панели навигации щелкните элемент **Conferencing** (Конференции), а затем **PIN Policy** (Политика ПИН-кодов).</span><span class="sxs-lookup"><span data-stu-id="835a4-131">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="835a4-132">На странице **PIN Policy** (Политика ПИН-кодов)  щелкните политику **Global** (Глобальная), нажмите кнопку **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).</span><span class="sxs-lookup"><span data-stu-id="835a4-132">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="835a4-p105">В поле **Minimum PIN length** (Минимальная длина ПИН-кода) окна **Edit PIN Policy** (Изменение политики ПИН-кодов) введите или выберите минимально допустимую длину ПИН-кода. По умолчанию установлена минимальная длина, равная пяти цифрам.</span><span class="sxs-lookup"><span data-stu-id="835a4-p105">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="835a4-p106">Чтобы указать максимальное число попыток входа, после превышения которого пользователь блокируется, установите флажок **Specify maximum logon attempts** (Указать максимальное число попыток входа). Если его не установить, максимально допустимое число попыток определяется автоматически на основании длины ПИН-кода. По умолчанию максимальное число попыток входа определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="835a4-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="835a4-138">Если флажок **Specify maximum logon attempts (Указать максимальное количество попыток входа)** установлен, в поле **Maximum logon attempts (Максимальное количество попыток входа)** введите или выберите максимальное количество попыток входа, которое планируется разрешить.</span><span class="sxs-lookup"><span data-stu-id="835a4-138">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="835a4-p107">Чтобы ПИН-коды имели конечный срок действия, установите флажок **Enable PIN expiration (Включить окончание срока действия ПИН-кодов)**. Если этот флажок не установить, то ПИН-коды будут бессрочными. По умолчанию ПИН-коды бессрочные.</span><span class="sxs-lookup"><span data-stu-id="835a4-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="835a4-142">Если флажок **Enable PIN expiration (Включить окончание срока действия ПИН-кодов)** установлен, в поле **PIN expires after (days) (Срок действия ПИН-кода истекает через (в днях)** введите или выберите количество дней, которое ПИН-код будет действительным.</span><span class="sxs-lookup"><span data-stu-id="835a4-142">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="835a4-p108">В поле **PIN history count (Счетчик журнала ПИН-кодов)** введите количество ПИН-кодов, которое должен создать пользователь, прежде чем сможет повторно использовать ПИН-код. По умолчанию пользователи могут повторно использовать свои ПИН-коды.</span><span class="sxs-lookup"><span data-stu-id="835a4-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="835a4-p109">Чтобы разрешить простые шаблоны цифр в ПИН-кодах, такие как последовательные или повторяющиеся цифры, установите флажок **Allow common patterns (Разрешить простые шаблоны)**. Если этот флажок не установлен, то разрешены только сложные шаблоны цифр. По умолчанию разрешены только сложные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="835a4-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="835a4-148">Из соображений безопасности Корпорация Майкрософт рекомендует не разрешать распространенные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="835a4-148">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="835a4-149">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="835a4-149">Click **Commit**.</span></span>
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="835a4-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="835a4-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="835a4-151">Чтобы изменить глобальную политику ПИН-кодов для телефонной видеоконференции, используйте cmdlet **Set-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="835a4-151">To modify the global dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="835a4-152">Следующая команда изменяет значение MinPasswordLength для всех политик ПИН-кодов, настроенных для использования в организации.</span><span class="sxs-lookup"><span data-stu-id="835a4-152">The following command changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization.</span></span> <span data-ttu-id="835a4-153">При этом команда сначала вызывает командлет **Get-CsPinPolicy** без каких-либо параметров для получения набора существующих политик PIN-кодов.</span><span class="sxs-lookup"><span data-stu-id="835a4-153">To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies.</span></span> <span data-ttu-id="835a4-154">Затем эта коллекция передается в cmdlet **Set-CsPinPolicy,** который изменяет значение свойства MinPasswordLength для каждой политики в коллекции:</span><span class="sxs-lookup"><span data-stu-id="835a4-154">That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

<span data-ttu-id="835a4-155">Дополнительные сведения, включая полное описание синтаксиса и список параметров, см. в описании [set-CsPinPolicy.](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="835a4-155">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="create-a-user-or-site-pin-policy"></a><span data-ttu-id="835a4-156">Создание политики ПИН-кодов для пользователя или сайта</span><span class="sxs-lookup"><span data-stu-id="835a4-156">Create a user or site PIN policy</span></span>

<span data-ttu-id="835a4-157">Вы можете создать политику ПИН-кодов пользователей или сайтов с помощью панели управления Skype для бизнеса Server или с помощью skype для бизнеса Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="835a4-157">You can create a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="835a4-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="835a4-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="835a4-159">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или которой назначена роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="835a4-159">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="835a4-160">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="835a4-160">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="835a4-161">В левой панели навигации щелкните элемент **Conferencing** (Конференц-связь), а затем щелкните элемент **PIN Policy** (Политика ПИН-кодов).</span><span class="sxs-lookup"><span data-stu-id="835a4-161">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="835a4-162">На странице **Политика ПИН-кодов** щелкните **Создать**, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="835a4-162">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="835a4-p111">Чтобы создать политику на уровне пользователя, щелкните **Политика пользователя**. В окне **Новая политика ПИН-кодов**, в поле **Имя**, введите имя, описывающее политику.</span><span class="sxs-lookup"><span data-stu-id="835a4-p111">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="835a4-p112">Чтобы создать политику на уровне сайта, щелкните **Политика сайта**. В поле поиска **Выбор сайта** введите все имя или часть имени сайта, для которого требуется создать политику. В списке сайтов щелкните необходимый сайт и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="835a4-p112">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="835a4-168">В поле **Описание** введите описание политики ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="835a4-168">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="835a4-p113">В поле **Minimum PIN length (Минимальная длина ПИН-кода)** введите или выберите минимальную длину ПИН-кода, которую планируется разрешить. По умолчанию минимальная длина — пять цифр.</span><span class="sxs-lookup"><span data-stu-id="835a4-p113">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="835a4-p114">Чтобы иметь возможность задавать максимальное количество попыток входа до блокировки пользователя, установите флажок **Specify maximum logon attempts (Указать максимальное количество попыток входа)**. Если этот флажок не установить, то максимальное количество разрешенных попыток определяется автоматически на основе длины ПИН-кода. По умолчанию максимальное количество попыток определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="835a4-p114">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="835a4-174">Если флажок **Specify maximum logon attempts (Указать максимальное количество попыток входа)** установлен, в поле **Maximum logon attempts (Максимальное количество попыток входа)** введите или выберите максимальное количество попыток входа, которое планируется разрешить.</span><span class="sxs-lookup"><span data-stu-id="835a4-174">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="835a4-p115">Чтобы ПИН-коды имели конечный срок действия, установите флажок **Enable PIN expiration (Включить окончание срока действия ПИН-кодов)**. Если этот флажок не установить, то ПИН-коды будут бессрочными. По умолчанию ПИН-коды бессрочные.</span><span class="sxs-lookup"><span data-stu-id="835a4-p115">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="835a4-178">Если флажок **Enable PIN expiration (Включить окончание срока действия ПИН-кодов)** установлен, в поле **PIN expires after (days) (Срок действия ПИН-кода истекает через (в днях)** введите или выберите количество дней, которое ПИН-код будет действительным.</span><span class="sxs-lookup"><span data-stu-id="835a4-178">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="835a4-p116">В поле **PIN history count (Счетчик журнала ПИН-кодов)** введите количество ПИН-кодов, которое должен создать пользователь, прежде чем сможет повторно использовать ПИН-код. По умолчанию пользователи могут повторно использовать свои ПИН-коды.</span><span class="sxs-lookup"><span data-stu-id="835a4-p116">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="835a4-p117">Чтобы разрешить простые шаблоны цифр в ПИН-кодах, такие как последовательные или повторяющиеся цифры, установите флажок **Allow common patterns (Разрешить простые шаблоны)**. Если этот флажок не установлен, то разрешены только сложные шаблоны цифр. По умолчанию разрешены только сложные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="835a4-p117">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="835a4-184">Из соображений безопасности Корпорация Майкрософт рекомендует не разрешать распространенные шаблоны.</span><span class="sxs-lookup"><span data-stu-id="835a4-184">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="835a4-185">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="835a4-185">Click **Commit**.</span></span>
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="835a4-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="835a4-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="835a4-187">Чтобы создать политику ПИН-кодов для пользователя или сайта, используйте **cmdlet New-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="835a4-187">To create a user or site PIN policy, use the **New-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="835a4-188">Следующая команда создает новую политику ПИН-кодов с идентификатором site:Redmond.</span><span class="sxs-lookup"><span data-stu-id="835a4-188">The following command creates a new PIN policy with the Identity site:Redmond.</span></span> <span data-ttu-id="835a4-189">Эта команда включает только один необязательный параметр MinPasswordLength, который используется для того, чтобы установить для свойства MinPasswordLength 7.</span><span class="sxs-lookup"><span data-stu-id="835a4-189">This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 7.</span></span> <span data-ttu-id="835a4-190">Все остальные свойства политики будут настраиваться с использованием значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="835a4-190">All the remaining policy properties will be configured using the default values.</span></span>
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 <span data-ttu-id="835a4-191">Дополнительные сведения, включая полное описание синтаксиса и список параметров, см. в описании [New-CsPinPolicy.](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="835a4-191">For more information, including a complete syntax description and list of parameters, see [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-a-user-or-site-pin-policy"></a><span data-ttu-id="835a4-192">Изменение политики ПИН-кодов пользователей или сайтов</span><span class="sxs-lookup"><span data-stu-id="835a4-192">Modify a user or site PIN policy</span></span>

<span data-ttu-id="835a4-193">Вы можете изменить политику ПИН-кодов пользователей или сайтов с помощью панели управления Skype для бизнеса Server или с помощью skype для бизнеса Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="835a4-193">You can modify a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="835a4-194">Изменение политики ПИН-кодов пользователей или сайтов с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="835a4-194">Modify a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="835a4-195">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или которой назначена роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="835a4-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="835a4-196">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="835a4-196">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="835a4-197">В левой панели навигации щелкните элемент **Conferencing** (Конференц-связь), а затем щелкните элемент **PIN Policy** (Политика ПИН-кодов).</span><span class="sxs-lookup"><span data-stu-id="835a4-197">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="835a4-198">На странице **Политика ПИН-кодов** выберите политику ПИН-кодов, которую требуется изменить, щелкните **Правка**, а затем — **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="835a4-198">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="835a4-199">В окне **Редактирование политики ПИН-кодов** измените необходимые параметры политики (кроме имени политики, которое невозможно изменить).</span><span class="sxs-lookup"><span data-stu-id="835a4-199">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>
    
6. <span data-ttu-id="835a4-200">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="835a4-200">Click **Commit**.</span></span>
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="835a4-201">Изменение политики ПИН-кодов пользователей или сайтов с помощью оболочки управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="835a4-201">Modify a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="835a4-202">Чтобы изменить политику ПИН-кодов для телефонной видеоконференции, используйте cmdlet **Set-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="835a4-202">To modify the dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="835a4-203">Следующая команда изменяет политику ПИН-кодов, назначенную сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="835a4-203">The following command modifies the PIN policy assigned to the Redmond site.</span></span> <span data-ttu-id="835a4-204">В этом случае команда изменяет значение свойства MinPasswordLength на 10; это означает, что новые ПИН-коды должны содержать не менее 10 цифр:</span><span class="sxs-lookup"><span data-stu-id="835a4-204">In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits:</span></span>
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

<span data-ttu-id="835a4-205">Дополнительные сведения, включая полное описание синтаксиса и список параметров, см. в описании [set-CsPinPolicy.](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="835a4-205">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="delete-a-user-or-site-pin-policy"></a><span data-ttu-id="835a4-206">Удаление политики ПИН-кодов пользователя или сайта</span><span class="sxs-lookup"><span data-stu-id="835a4-206">Delete a user or site PIN policy</span></span>

<span data-ttu-id="835a4-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="835a4-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="835a4-208">Удаление политики ПИН-кодов пользователей или сайтов с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="835a4-208">Delete a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="835a4-209">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или которой назначена роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="835a4-209">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="835a4-210">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="835a4-210">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="835a4-211">В левой панели навигации щелкните элемент **Conferencing** (Конференц-связь), а затем щелкните элемент **PIN Policy** (Политика ПИН-кодов).</span><span class="sxs-lookup"><span data-stu-id="835a4-211">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="835a4-212">На странице **"Политика ПИН-кодов"** щелкните политику ПИН-кодов, которую необходимо изменить, нажмите кнопку "Изменить" и выберите **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="835a4-212">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Delete**.</span></span>
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="835a4-213">Удаление политики ПИН-кодов пользователей или сайтов с помощью skype для бизнеса Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="835a4-213">Delete a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="835a4-214">Чтобы удалить политику ПИН-кодов пользователей или сайтов, используйте **cmdlet Remove-CsPinPolicy.**</span><span class="sxs-lookup"><span data-stu-id="835a4-214">To delete a user or site PIN policy, use the **Remove-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="835a4-215">Следующая команда удаляет все политики ПИН-кодов, настроенные на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="835a4-215">The following command removes all the PIN policies that have been configured at the site scope.</span></span> <span data-ttu-id="835a4-216">Для этого используйте с помощью cmdlet **Get-CsPinPolicy** вместе с параметром Filter коллекцию всех политик, идентификатор которых начинается с символов "site:".</span><span class="sxs-lookup"><span data-stu-id="835a4-216">To do this, use the **Get-CsPinPolicy** cmdlet, along with the Filter parameter, to return a collection of all the policies that have an Identity that begins with the characters "site:".</span></span> <span data-ttu-id="835a4-217">Затем эта коллекция передается по конвейеру в cmdlet **Remove-CsPinPolicy,** который удаляет все политики в коллекции:</span><span class="sxs-lookup"><span data-stu-id="835a4-217">This collection is then piped to the **Remove-CsPinPolicy** cmdlet, which deletes each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

<span data-ttu-id="835a4-218">Дополнительные сведения, включая полное описание синтаксиса и список параметров, см. в описании [remove-CsPinPolicy.](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="835a4-218">For more information, including a complete syntax description and list of parameters, see [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span></span>
  

