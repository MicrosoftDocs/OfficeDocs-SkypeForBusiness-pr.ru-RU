---
title: Управление политиками ПИН для конференц-связи с телефонным подключением в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Сводка: сведения о том, как управлять политиками ПИН для конференц-связи с телефонным подключением в Skype для бизнеса Server.'
ms.openlocfilehash: f5ffef4af17a4337fe600b2059aab1ea106235ae
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992296"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="77414-103">Управление политиками ПИН для конференц-связи с телефонным подключением в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="77414-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="77414-104">**Сводка:** Сведения о том, как управлять политиками ПИН для конференц-связи с телефонным подключением в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="77414-104">**Summary:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="77414-105">Пользователи Skype для бизнеса Server, у которых есть учетные данные доменных служб Active Directory (AD DS), могут присоединиться к конференциям с телефонным подключением в качестве пользователей, прошедших проверку подлинности, используя персональный идентификационный номер (PIN).</span><span class="sxs-lookup"><span data-stu-id="77414-105">Skype for Business Server users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="77414-106">Политика ПИН-кодов определяет способ работы ПИН-кодов для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="77414-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>
  
 <span data-ttu-id="77414-p102">Если вы хотите применить одну и ту же политику ПИН-кодов ко всей организации, вы можете использовать глобальную политику ПИН-кодов, изменив ее так, как нужно. Глобальная политика ПИН-кодов определяет правила для ПИН-кодов конференц-связи с телефонным подключением на уровне лесов. Глобальную политику ПИН-кодов можно изменить, но ее нельзя удалить.</span><span class="sxs-lookup"><span data-stu-id="77414-p102">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed. The global PIN policy defines the rules for dial-in conferencing PINs at the forest level. You can modify the global PIN policy, but you cannot delete it.</span></span>
  
<span data-ttu-id="77414-110">Чтобы применить особую политику к узлу или группе пользователей, вы можете создать новую политику ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="77414-110">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span>
  
<span data-ttu-id="77414-111">Политики ПИН-кодов применяются к пользователям в очередности от самой узкой области действия до самой широкой.</span><span class="sxs-lookup"><span data-stu-id="77414-111">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="77414-112">Если вы назначили пользователю политику ПИН-кодов на уровне пользователя, ее параметры имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="77414-112">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="77414-113">Если вы не назначили политику пользователя, применяется политика ПИН-кодов на уровне узла, если она определена.</span><span class="sxs-lookup"><span data-stu-id="77414-113">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="77414-114">Если политики пользователя и узла не назначены, действуют параметры по умолчанию глобальной политики ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="77414-114">If no user or site policies apply, global PIN policy provides the default settings.</span></span>
  
## <a name="view-information-about-pin-policies"></a><span data-ttu-id="77414-115">Просмотр сведений о политиках ПИН-кодов</span><span class="sxs-lookup"><span data-stu-id="77414-115">View information about PIN policies</span></span>

<span data-ttu-id="77414-116">Сведения о политиках закрепления можно просмотреть с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="77414-116">You can view information about PIN policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="77414-117">Просмотр сведений о политиках закрепления с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="77414-117">View information about PIN policies by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="77414-118">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .</span><span class="sxs-lookup"><span data-stu-id="77414-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="77414-119">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="77414-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="77414-120">В левой панели навигации щелкните элемент **Конференц-связь**, а затем щелкните элемент **Политика ПИН-кодов**.</span><span class="sxs-lookup"><span data-stu-id="77414-120">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="77414-121">На странице **Политика ПИН-кодов** выберите политику ПИН-кодов, которую требуется просмотреть, щелкните **Правка**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="77414-121">On the **PIN Policy** page, click the PIN policy that you want to view, click **Edit**, and then click **Show details**.</span></span>
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="77414-122">Просмотр сведений о политиках закрепления с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="77414-122">View information about PIN policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="77414-123">Для просмотра сведений о политиках ПИН-кодов используйте командлет **Get-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="77414-123">To view information about PIN policies, use the **Get-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="77414-124">Например, следующая команда возвращает сведения об одной политике ПИН-кода с идентификатором site:Redmond:</span><span class="sxs-lookup"><span data-stu-id="77414-124">For example, the following command returns information about a single PIN policy with the Identity site:Redmond:</span></span>
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

<span data-ttu-id="77414-125">Дополнительные сведения, включая полные описания синтаксиса и список параметров, можно найти в [статьях Get-кспинполици](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="77414-125">For more information, including a complete syntax description and list of parameters, see [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-the-global-pin-policy"></a><span data-ttu-id="77414-126">Изменение глобальной политики ПИН-кодов</span><span class="sxs-lookup"><span data-stu-id="77414-126">Modify the global PIN policy</span></span>

<span data-ttu-id="77414-127">Вы можете изменить глобальную политику ПИН-кода с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для Business Server Management.</span><span class="sxs-lookup"><span data-stu-id="77414-127">You can modify the global PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="77414-128">Изменение политики ПИН-кода для глобальной конференции с телефонным подключением с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="77414-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="77414-129">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .</span><span class="sxs-lookup"><span data-stu-id="77414-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="77414-130">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="77414-130">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="77414-131">В левой панели навигации щелкните элемент **Конференц-связь**, а затем щелкните элемент **Политика ПИН-кодов**.</span><span class="sxs-lookup"><span data-stu-id="77414-131">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="77414-132">На странице **Политика ПИН-кодов** щелкните политику **Глобальная**, нажмите кнопку **Изменить** и затем щелкните **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="77414-132">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="77414-p105">В окне **Изменение политики ПИН-кода** введите или выберите в поле **Минимальная длина ПИН-кода** минимальную длину ПИН-кода. Минимальная длина по умолчанию составляет пять цифр.</span><span class="sxs-lookup"><span data-stu-id="77414-p105">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="77414-p106">Чтобы иметь возможность задать максимальное число попыток входа перед блокированием пользователя, установите флажок **Задать максимальное число попыток входа**. Если этот параметр не выбран, максимальное число разрешенных попыток входа автоматически определяется в зависимости от длины ПИН-кода. По умолчанию максимальное число попыток определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="77414-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="77414-138">Если установлен флажок **Задать максимальное число попыток входа**, в поле **Максимальное число попыток входа** введите или выберите максимальное число попыток входа, которое требуется разрешить.</span><span class="sxs-lookup"><span data-stu-id="77414-138">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="77414-p107">Чтобы ПИН-коды имели конечный срок действия, установите флажок **Включить конечный срок действия ПИН-кодов**. Если этот параметр не выбран, ПИН-коды не будут иметь ограничений по сроку действия. По умолчанию ПИН-коды не имеют ограничений по сроку действия.</span><span class="sxs-lookup"><span data-stu-id="77414-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="77414-142">Если флажок **Разрешить окончание срока действия ПИН-кода** установлен, то в поле **Срок действия ПИН-кода истекает после (дней)** введите или выберите максимальное число дней, после которых ПИН-коды становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="77414-142">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="77414-p108">В поле **История значений ПИН-кода** введите число ПИН-кодов, которое пользователь должен создать перед тем, как он сможет использовать их повторно. По умолчанию пользователи могут повторно использовать ПИН-коды.</span><span class="sxs-lookup"><span data-stu-id="77414-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="77414-p109">Чтобы разрешить распространенные последовательности цифр в ПИН-кодах, такие как последовательные номера и повторяющиеся наборы номеров, установите флажок **Разрешить общие шаблоны**. Если не выбрать этот параметр, будут разрешены только сложные наборы цифр. По умолчанию разрешены только сложные наборы цифр.</span><span class="sxs-lookup"><span data-stu-id="77414-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="77414-148">В целях безопасности Microsoft рекомендует не разрешать использование распространенных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="77414-148">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="77414-149">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="77414-149">Click **Commit**.</span></span>
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="77414-150">Изменение политики ПИН-кода для глобальной конференции с телефонным подключением с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="77414-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="77414-151">Для изменения глобальной политики ПИН-кодов для конференц-связи с телефонным подключением используйте командлет **Set-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="77414-151">To modify the global dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="77414-p110">Следующая команда изменяет значение свойства MinPasswordLength для всех политик ПИН-кодов, настроенных для использования в организации. При этом команда сначала вызывает командлет **Get-CsPinPolicy** без каких-либо параметров для получения набора существующих политик ПИН-кодов. Этот набор затем передается в командлет **Set-CsPinPolicy**, который изменяет значение свойства MinPasswordLength для каждой политики в наборе.</span><span class="sxs-lookup"><span data-stu-id="77414-p110">The following command changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization. To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies. That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

<span data-ttu-id="77414-155">Дополнительные сведения, в том числе полные описания синтаксиса и список параметров, приведены в разделе [Set-кспинполици](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="77414-155">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="create-a-user-or-site-pin-policy"></a><span data-ttu-id="77414-156">Создание политики ПИН-кодов для пользователя или сайта</span><span class="sxs-lookup"><span data-stu-id="77414-156">Create a user or site PIN policy</span></span>

<span data-ttu-id="77414-157">Вы можете создать политику ПИН-кода пользователя или сайта с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="77414-157">You can create a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="77414-158">Создание политики ПИН-кода для пользователя или сайта с помощью панели управления "Skype для бизнеса Server"</span><span class="sxs-lookup"><span data-stu-id="77414-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="77414-159">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .</span><span class="sxs-lookup"><span data-stu-id="77414-159">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="77414-160">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="77414-160">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="77414-161">В левой панели навигации щелкните элемент **Конференц-связь**, а затем щелкните элемент **Политика ПИН-кодов**.</span><span class="sxs-lookup"><span data-stu-id="77414-161">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="77414-162">На странице **Политика в отношении ПИН-кодов** щелкните **Создать**, а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="77414-162">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="77414-p111">Чтобы создать политику на уровне пользователя, щелкните **Политика пользователя**. В окне **Новая политика в отношении ПИН-кодов**, в поле **Имя**, введите имя, описывающее политику.</span><span class="sxs-lookup"><span data-stu-id="77414-p111">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="77414-p112">Чтобы создать политику уровня сайта, выберите вариант **Политика сайта**. В поле поиска **Выбор сайта** введите часть или полное имя сайта, для которого требуется создать политику. В списке сайтов выберите нужный сайт и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="77414-p112">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="77414-168">В поле **Описание** введите описание политики в отношении ПИН-кодов.</span><span class="sxs-lookup"><span data-stu-id="77414-168">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="77414-p113">В поле **Минимальная длина ПИН-кода** введите или выберите минимальную длину ПИН-кода, которую требуется разрешить. Минимальная длина по умолчанию составляет пять цифр.</span><span class="sxs-lookup"><span data-stu-id="77414-p113">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="77414-p114">Чтобы иметь возможность задать максимальное число попыток входа перед блокированием пользователя, установите флажок **Задать максимальное число попыток входа**. Если этот параметр не выбран, максимальное число разрешенных попыток входа автоматически определяется в зависимости от длины ПИН-кода. По умолчанию максимальное число попыток определяется автоматически.</span><span class="sxs-lookup"><span data-stu-id="77414-p114">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="77414-174">Если установлен флажок **Задать максимальное число попыток входа**, в поле **Максимальное число попыток входа** введите или выберите максимальное число попыток входа, которое требуется разрешить.</span><span class="sxs-lookup"><span data-stu-id="77414-174">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="77414-p115">Чтобы ПИН-коды имели конечный срок действия, установите флажок **Включить конечный срок действия ПИН-кодов**. Если этот параметр не выбран, ПИН-коды не будут иметь ограничений по сроку действия. По умолчанию ПИН-коды не имеют ограничений по сроку действия.</span><span class="sxs-lookup"><span data-stu-id="77414-p115">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="77414-178">Если флажок **Разрешить окончание срока действия ПИН-кода** установлен, то в поле **Срок действия ПИН-кода истекает после (дней)** введите или выберите максимальное число дней, после которых ПИН-коды становятся недействительными.</span><span class="sxs-lookup"><span data-stu-id="77414-178">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="77414-p116">В поле **История значений ПИН-кода** введите число ПИН-кодов, которое пользователь должен создать перед тем, как он сможет использовать их повторно. По умолчанию пользователи могут повторно использовать ПИН-коды.</span><span class="sxs-lookup"><span data-stu-id="77414-p116">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="77414-p117">Чтобы разрешить распространенные последовательности цифр в ПИН-кодах, такие как последовательные номера и повторяющиеся наборы номеров, установите флажок **Разрешить общие шаблоны**. Если не выбрать этот параметр, будут разрешены только сложные наборы цифр. По умолчанию разрешены только сложные наборы цифр.</span><span class="sxs-lookup"><span data-stu-id="77414-p117">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="77414-184">В целях безопасности Microsoft рекомендует не разрешать использование распространенных последовательностей.</span><span class="sxs-lookup"><span data-stu-id="77414-184">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="77414-185">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="77414-185">Click **Commit**.</span></span>
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="77414-186">Создание политики для ПИН-кода пользователя или сайта с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="77414-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="77414-187">Для создания политики ПИН-кодов для пользователя или сайта используйте командлет **New-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="77414-187">To create a user or site PIN policy, use the **New-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="77414-p118">Следующая команда создает новую политику ПИН-кодов с идентификатором site:Redmond. Эта команда включает только один дополнительный параметр, MinPasswordLength, который используется для установки свойства MinPasswordLength в значение 7. Все остальные свойства политики будут настраиваться с использованием значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="77414-p118">The following command creates a new PIN policy with the Identity site:Redmond. This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 7. All the remaining policy properties will be configured using the default values.</span></span>
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 <span data-ttu-id="77414-191">Дополнительные сведения, в том числе полные описания синтаксиса и список параметров, можно найти в разделе [New-кспинполици](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="77414-191">For more information, including a complete syntax description and list of parameters, see [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-a-user-or-site-pin-policy"></a><span data-ttu-id="77414-192">Изменение политики ПИН-кодов для пользователя или сайта</span><span class="sxs-lookup"><span data-stu-id="77414-192">Modify a user or site PIN policy</span></span>

<span data-ttu-id="77414-193">Вы можете изменить политику ПИН-кода пользователя или сайта с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для Business Server Management.</span><span class="sxs-lookup"><span data-stu-id="77414-193">You can modify a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="77414-194">Изменение политики закрепления пользователей и сайтов с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="77414-194">Modify a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="77414-195">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .</span><span class="sxs-lookup"><span data-stu-id="77414-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="77414-196">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="77414-196">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="77414-197">В левой панели навигации щелкните элемент **Конференц-связь**, а затем щелкните элемент **Политика ПИН-кодов**.</span><span class="sxs-lookup"><span data-stu-id="77414-197">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="77414-198">На странице **Политика ПИН-кодов** выберите политику ПИН-кодов, которую требуется изменить, щелкните **Правка**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="77414-198">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="77414-199">В окне **Редактирование политики ПИН-кодов** измените необходимые параметры политики (кроме имени политики, которое невозможно изменить).</span><span class="sxs-lookup"><span data-stu-id="77414-199">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>
    
6. <span data-ttu-id="77414-200">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="77414-200">Click **Commit**.</span></span>
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="77414-201">Изменение политики закрепления пользователей и сайтов с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="77414-201">Modify a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="77414-202">Для изменения политики ПИН-кодов для конференц-связи с телефонным подключением используйте командлет **Set-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="77414-202">To modify the dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="77414-p119">Следующая команда изменяет политику ПИН-кода, назначенную сайту Redmond. В этом случае команда изменяет значение свойства MinPasswordLength на 10; это означает, что новые ПИН-коды должны содержать по крайней мере 10 цифр:</span><span class="sxs-lookup"><span data-stu-id="77414-p119">The following command modifies the PIN policy assigned to the Redmond site. In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits:</span></span>
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

<span data-ttu-id="77414-205">Дополнительные сведения, в том числе полные описания синтаксиса и список параметров, приведены в разделе [Set-кспинполици](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="77414-205">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="delete-a-user-or-site-pin-policy"></a><span data-ttu-id="77414-206">Удаление политики ПИН-кодов для пользователя или сайта</span><span class="sxs-lookup"><span data-stu-id="77414-206">Delete a user or site PIN policy</span></span>

<span data-ttu-id="77414-207">Вы можете удалить политику закрепления пользователя или сайта с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для Business Server Management.</span><span class="sxs-lookup"><span data-stu-id="77414-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="77414-208">Удаление политики закрепления пользователей и сайтов с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="77414-208">Delete a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="77414-209">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .</span><span class="sxs-lookup"><span data-stu-id="77414-209">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="77414-210">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="77414-210">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="77414-211">В левой панели навигации щелкните элемент **Конференц-связь**, а затем щелкните элемент **Политика ПИН-кодов**.</span><span class="sxs-lookup"><span data-stu-id="77414-211">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="77414-212">На странице **Политика ПИН-кодов** выберите политику ПИН-кодов, которую требуется изменить, щелкните **Правка**, а затем щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="77414-212">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Delete**.</span></span>
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="77414-213">Удаление политики ПИН-кода пользователя или сайта с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="77414-213">Delete a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="77414-214">Для удаления политики ПИН-кодов для пользователя или сайта используйте командлет **Remove-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="77414-214">To delete a user or site PIN policy, use the **Remove-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="77414-p120">Следующая команда удаляет все политики ПИН-кодов, которые настроены в области сайта. Для этого используется командлет **Get-CsPinPolicy** с параметром Filter, чтобы получить коллекцию всех политик, свойство Identity которых начинается с "site:". Эта коллекция затем передается командлету **Remove-CsPinPolicy**, который удаляет все политики в коллекции:</span><span class="sxs-lookup"><span data-stu-id="77414-p120">The following command removes all the PIN policies that have been configured at the site scope. To do this, use the **Get-CsPinPolicy** cmdlet, along with the Filter parameter, to return a collection of all the policies that have an Identity that begins with the characters "site:". This collection is then piped to the **Remove-CsPinPolicy** cmdlet, which deletes each policy in the collection:</span></span>
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

<span data-ttu-id="77414-218">Дополнительные сведения, в том числе полные описания синтаксиса и список параметров, приведены в разделе [Remove-кспинполици](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="77414-218">For more information, including a complete syntax description and list of parameters, see [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span></span>
  

