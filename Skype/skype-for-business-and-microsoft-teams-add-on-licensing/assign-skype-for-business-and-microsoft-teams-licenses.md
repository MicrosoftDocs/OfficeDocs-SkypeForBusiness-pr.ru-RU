---
title: "Назначение лицензий Skype для бизнеса и Microsoft Teams"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.date: 01/22/2018
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
- Strat_SB_PSTN
description: "Узнайте, как назначить Скайп для бизнеса лицензий для телефонной системой, звук конференц-связи, вызов планы и кредитов коммуникаций. "
ms.openlocfilehash: a5cbc36d1b5ce5a7d79587df369b2d3bf3caacd6
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="1cc81-103">Назначение лицензий Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1cc81-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="1cc81-p101">В этой статье приводятся советы назначение лицензий пользователям для таких функций, как аудиоконференции, телефонной системой и вызов планов. Он также предоставляет сценарии для назначения лицензий в пакетном режиме.</span><span class="sxs-lookup"><span data-stu-id="1cc81-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span></span>
  
 <span data-ttu-id="1cc81-106">**Важно**: см. [Скайп для бизнеса и группами Майкрософт дополнительный компонент лицензирования](skype-for-business-and-microsoft-teams-add-on-licensing.md) для получения сведений о что лицензируемые вам необходимо купить и **как приобрести** их - в зависимости от плана Office 365 — так что пользователи получают звук конференц-связи, обслуживание бесплатных номеров и возможность звонить по номерам за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1cc81-106">**IMPORTANT**: See [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="1cc81-107">Телефонные системы и планы звонков. Советы и сценарии по назначению лицензий</span><span class="sxs-lookup"><span data-stu-id="1cc81-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="1cc81-108">Что нужно знать, прежде чем назначение аудиоконференции, телефонной системой и вызов планирование лицензий</span><span class="sxs-lookup"><span data-stu-id="1cc81-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="1cc81-p102">**При использовании локальных подключений ТСОП для пользователей в гибридных средах** необходимо назначить только лицензию на **телефонную систему**. Назначать план звонков **НЕ НУЖНО**.</span><span class="sxs-lookup"><span data-stu-id="1cc81-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>
    
- <span data-ttu-id="1cc81-112">**Задержка после назначения лицензий**: из-за задержки между Office 365 и Скайп для бизнеса в Интернет, возможно может потребоваться до 24 часов для пользователя, чтобы назначить вызов планирование после назначении лицензии.</span><span class="sxs-lookup"><span data-stu-id="1cc81-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="1cc81-113">Если после 24 часов пользователя не будет назначен вызов планирование, пожалуйста, [обращение в службу поддержки продуктов бизнес - Admin справки](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="1cc81-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>
    
- <span data-ttu-id="1cc81-p104">**Сообщения об ошибках**. Если приобретено неправильное число лицензий, выдается сообщение об ошибке. Если требуется приобрести дополнительные лицензии на планы звонков, щелкните **Купить еще**.</span><span class="sxs-lookup"><span data-stu-id="1cc81-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="1cc81-116">**Дальнейшие действия**: после назначения лицензий на вызов планирование для пользователей, необходимо получить номера телефонов для вашей организации, а затем назначить эти номера для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1cc81-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="1cc81-117">Для получения пошаговых инструкций см [вызов планов](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="1cc81-117">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="1cc81-118">Назначение лицензии на телефонную систему и план звонков одному пользователю</span><span class="sxs-lookup"><span data-stu-id="1cc81-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="1cc81-p106">Шаги совпадают с шагами при назначении лицензии на Office 365. См. раздел [Управление лицензиями Office 365 бизнес](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="1cc81-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="1cc81-121">Массовое назначение лицензий на телефонную систему и план звонков</span><span class="sxs-lookup"><span data-stu-id="1cc81-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="1cc81-122">Установка **Microsoft Online Services помощник по входу для ИТ-специалистов RTW**.</span><span class="sxs-lookup"><span data-stu-id="1cc81-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="1cc81-123">Не установлен модуль?</span><span class="sxs-lookup"><span data-stu-id="1cc81-123">Don't have the module installed?</span></span> <span data-ttu-id="1cc81-124">В разделе [Microsoft Online Services помощника по входу для RTW специалистам ИТ](https://go.microsoft.com/fwlink/?LinkId=625123) для его загрузки.</span><span class="sxs-lookup"><span data-stu-id="1cc81-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>
    
2. <span data-ttu-id="1cc81-125">Установка **модуль Windows Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="1cc81-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="1cc81-126">Не установлен модуль?</span><span class="sxs-lookup"><span data-stu-id="1cc81-126">Don't have the module installed?</span></span> <span data-ttu-id="1cc81-127">В разделе [Управление Azure AD, с помощью Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) синтаксис командлета и инструкции по загрузке.</span><span class="sxs-lookup"><span data-stu-id="1cc81-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
3. <span data-ttu-id="1cc81-128">После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="1cc81-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
  <span data-ttu-id="1cc81-129">В этом примере **лицензия "Корпоративный E3"** назначается вместе с лицензией на **телефонную систему** и **план внутренних звонков**.</span><span class="sxs-lookup"><span data-stu-id="1cc81-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>
    
  <span data-ttu-id="1cc81-130">Названия лицензий и наименования продуктов в сценарии выделены курсивом. См. раздел **Названия продуктов и номера SKU для телефонной системы и плана звонков, используемые для сценариев** после примера.</span><span class="sxs-lookup"><span data-stu-id="1cc81-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>
    
  ```
  #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
  
  #Example of text file:
  #user1@domain.com
  #user2@domain.com
  
  #Import Module
  ipmo MSOnline
  #Authenticate to MSOLservice.
  Connect-MSOLService
  #File prompt to select the userlist txt file.
  [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
  $OFD = New-Object System.Windows.Forms.OpenFileDialog
  $OFD.filter = "text files (*.*)| *.txt"
  $OFD.ShowDialog() | Out-Null
  $OFD.filename
  If ($OFD.filename -eq '')
  {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
  }
  #Create a variable of all users.
  $users = Get-Content $OFD.filename
  #License each user in the $users variable.
  #Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
  International Calling.
  for each ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    } 
  ```
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="1cc81-131">Названия продуктов и номера SKU для телефонной системы и плана звонков, использующиеся для сценариев</span><span class="sxs-lookup"><span data-stu-id="1cc81-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="1cc81-132">**Наименование товара**</span><span class="sxs-lookup"><span data-stu-id="1cc81-132">**Product name**</span></span>|<span data-ttu-id="1cc81-133">**Наименование товарной единицы**</span><span class="sxs-lookup"><span data-stu-id="1cc81-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1cc81-134">Корпоративный E5 (с телефонной системой)</span><span class="sxs-lookup"><span data-stu-id="1cc81-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="1cc81-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="1cc81-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="1cc81-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="1cc81-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="1cc81-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="1cc81-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="1cc81-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="1cc81-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="1cc81-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="1cc81-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="1cc81-140">Skype для бизнеса Online Standalone Plan 2</span><span class="sxs-lookup"><span data-stu-id="1cc81-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="1cc81-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="1cc81-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="1cc81-142">Телефонная система</span><span class="sxs-lookup"><span data-stu-id="1cc81-142">Phone System</span></span>  <br/> |<span data-ttu-id="1cc81-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="1cc81-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="1cc81-144">План международных звонков</span><span class="sxs-lookup"><span data-stu-id="1cc81-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="1cc81-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="1cc81-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="1cc81-146">План внутренних звонков</span><span class="sxs-lookup"><span data-stu-id="1cc81-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="1cc81-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="1cc81-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="1cc81-148">Кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="1cc81-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="1cc81-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="1cc81-149">MCOPSTNPP</span></span>  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="1cc81-150">Аудиоконференция. Советы и сценарии для назначения лицензий</span><span class="sxs-lookup"><span data-stu-id="1cc81-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="1cc81-151">Что нужно знать перед назначением лицензий на аудиоконференцию</span><span class="sxs-lookup"><span data-stu-id="1cc81-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="1cc81-p109">**Сторонний поставщик аудиоконференций**. Если для пользователя уже настроено использование стороннего поставщика аудиоконференций, при назначении ему лицензии на **аудиоконференцию** поставщиком аудиоконференций автоматически назначается Майкрософт, но вы можете снова задать стороннего поставщика.</span><span class="sxs-lookup"><span data-stu-id="1cc81-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span></span>
    
- <span data-ttu-id="1cc81-154">Дальнейшие действия: после назначения лицензий **Аудиоконференций** , им необходимо назначить поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="1cc81-154">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="1cc81-155">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="1cc81-155">Do one of the following:</span></span>
    
  - [<span data-ttu-id="1cc81-156">Назначение Майкрософт в качестве поставщика услуг аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="1cc81-156">Assign Microsoft as the audio conferencing provider</span></span>](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - <span data-ttu-id="1cc81-157">[Назначение стороннего поставщика услуг аудиоконференций](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)</span><span class="sxs-lookup"><span data-stu-id="1cc81-157">Or, [Assign a third-party as the audio conferencing provider](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)</span></span>
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="1cc81-158">Назначение лицензии на аудиоконференции одному пользователю</span><span class="sxs-lookup"><span data-stu-id="1cc81-158">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="1cc81-p111">Шаги совпадают с шагами при назначении лицензии на Office 365. См. раздел [Управление лицензиями Office 365 бизнес](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="1cc81-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="1cc81-161">Массовое назначение лицензий на аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="1cc81-161">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="1cc81-162">Скачайте и установите [Помощник по входу в Microsoft Online Services для ИТ-специалистов, версия RTW ](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="1cc81-162">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>
    
2. <span data-ttu-id="1cc81-p112">Загрузите и установите **модуль Windows Azure Active Directory**. Инструкции по установке и синтаксис командлетов см. в разделе[Управление службой Azure AD с помощью Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="1cc81-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
    <span data-ttu-id="1cc81-165">После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="1cc81-165">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
    <span data-ttu-id="1cc81-166">Имя лицензии или названия продуктов в скрипте, перечислены в текста курсивом.</span><span class="sxs-lookup"><span data-stu-id="1cc81-166">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="1cc81-167">В разделе [имена аудиоконференции продукта или номера SKU, используемый для скриптов](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) для всех названия продуктов.</span><span class="sxs-lookup"><span data-stu-id="1cc81-167">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>
    
    <span data-ttu-id="1cc81-168">В этом примере лицензия "Корпоративный E3" назначается вместе с лицензией на аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="1cc81-168">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>
    
```
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline

#Authenticate to MSOLservice
Connect-MSOLService
#File prompt to select the userlist txt file
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
  $OFD = New-Object System.Windows.Forms.OpenFileDialog
  $OFD.filter = "text files (*.*)| *.txt"
  $OFD.ShowDialog() | Out-Null
  $OFD.filename

If ($OFD.filename -eq '')
{
Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}

#Create a variable of all users
$users = Get-Content $OFD.filename

#License each user in the $users variable
foreach ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
    } 
```

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="1cc81-169">Названия продуктов и номера SKU для аудиоконференций, использующихся для сценариев</span><span class="sxs-lookup"><span data-stu-id="1cc81-169">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="1cc81-170"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="1cc81-170"></span></span>

|<span data-ttu-id="1cc81-171">**Наименование товара**</span><span class="sxs-lookup"><span data-stu-id="1cc81-171">**Product name**</span></span>|<span data-ttu-id="1cc81-172">**Наименование товарной единицы**</span><span class="sxs-lookup"><span data-stu-id="1cc81-172">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1cc81-173">Аудиоконференция</span><span class="sxs-lookup"><span data-stu-id="1cc81-173">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="1cc81-174">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="1cc81-174">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="1cc81-175">Skype для бизнеса Online Standalone Plan 2</span><span class="sxs-lookup"><span data-stu-id="1cc81-175">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="1cc81-176">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="1cc81-176">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="1cc81-177">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="1cc81-177">Enterprise E1</span></span>  <br/> |<span data-ttu-id="1cc81-178">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="1cc81-178">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="1cc81-179">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="1cc81-179">Enterprise E3</span></span>  <br/> |<span data-ttu-id="1cc81-180">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="1cc81-180">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="1cc81-181">Корпоративный E5 (без аудиоконференции)</span><span class="sxs-lookup"><span data-stu-id="1cc81-181">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="1cc81-182">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="1cc81-182">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="1cc81-183">Корпоративный E5 (с аудиоконференцией)</span><span class="sxs-lookup"><span data-stu-id="1cc81-183">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="1cc81-184">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="1cc81-184">ENTERPRISEPREMIUM</span></span>  <br/> |
   
## <a name="communications-credits"></a><span data-ttu-id="1cc81-185">Кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="1cc81-185">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="1cc81-186">Что нужно знать перед назначением лицензий на кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="1cc81-186">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="1cc81-187">**E5 корпоративных клиентов**: даже в том случае, если пользователи назначаются E5 корпоративных лицензий, все же рекомендуется назначить их **Кредитов Communications** лицензий.</span><span class="sxs-lookup"><span data-stu-id="1cc81-187">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="1cc81-188">**Дальнейшие действия**: после назначить эти лицензии, необходимо получить номера телефонов для вашей организации, а затем назначить эти номера для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1cc81-188">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="1cc81-189">Для получения пошаговых инструкций см [вызов планов](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="1cc81-189">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="1cc81-190">Назначение лицензии на кредиты на связь одному пользователю</span><span class="sxs-lookup"><span data-stu-id="1cc81-190">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="1cc81-p115">Шаги совпадают с шагами при назначении лицензии на Office 365. См. раздел [Управление лицензиями Office 365 бизнес](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="1cc81-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="1cc81-193">Назначение лицензий кредитов коммуникаций в пакетном режиме</span><span class="sxs-lookup"><span data-stu-id="1cc81-193">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="1cc81-p116">Ознакомьтесь с примером сценария для назначения лицензий на **аудиоконференции**. Обновите сведения для назначения лицензий на **кредиты на связь**.</span><span class="sxs-lookup"><span data-stu-id="1cc81-p116">Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1cc81-196">See also</span><span class="sxs-lookup"><span data-stu-id="1cc81-196">Related topics</span></span>

[<span data-ttu-id="1cc81-197">Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1cc81-197">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)
  
[<span data-ttu-id="1cc81-198">Настройка планов звонков</span><span class="sxs-lookup"><span data-stu-id="1cc81-198">Set up Calling Plans</span></span>](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[<span data-ttu-id="1cc81-199">Добавление средств и управление кредитами на связь</span><span class="sxs-lookup"><span data-stu-id="1cc81-199">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
  