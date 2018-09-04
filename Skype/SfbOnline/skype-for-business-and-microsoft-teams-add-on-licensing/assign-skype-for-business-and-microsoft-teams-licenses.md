---
title: Назначение лицензий Skype для бизнеса и Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Licensing
description: 'Узнайте, как назначить лицензии Skype для бизнеса на телефонные системы, аудиоконференции, планы звонков и кредиты на связь. '
ms.openlocfilehash: fef4bea3971f2984e46de7a3592b1a157076c879
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780670"
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="4229d-103">Назначение лицензий Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4229d-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="4229d-104">В этой статье приводятся советы по назначению пользователям лицензий на аудиоконференции, телефонную систему и тарифные планы.</span><span class="sxs-lookup"><span data-stu-id="4229d-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System and Calling Plans.</span></span> <span data-ttu-id="4229d-105">Здесь также представлены сценарии для массового назначения лицензий.</span><span class="sxs-lookup"><span data-stu-id="4229d-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4229d-106">Сведения о том, какие лицензии нужны и **как их приобрести** в зависимости от плана Office 365, чтобы пользователи могли получить доступ к аудиоконференциям, бесплатным номерам, а также могли звонить за пределы организации, см. в статье [Лицензирование надстроек Skype для бизнеса и Microsoft Teams](skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="4229d-106">IMPORTANT: See[Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="4229d-107">Телефонные системы и тарифные планы. Советы и сценарии по назначению лицензий</span><span class="sxs-lookup"><span data-stu-id="4229d-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="4229d-108">Что нужно знать перед назначением лицензий на аудиоконференции, телефонную систему и тарифный план</span><span class="sxs-lookup"><span data-stu-id="4229d-108">What you need to know before assigning Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="4229d-p102">**При использовании локальных подключений ТСОП для пользователей в гибридных средах** необходимо назначить только лицензию на **телефонную систему**. Назначать план звонков **НЕ НУЖНО**.</span><span class="sxs-lookup"><span data-stu-id="4229d-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="4229d-112">**Задержка после назначения лицензий**. Из-за задержки передачи данных между системами Office 365 и Skype для бизнеса Online назначение тарифного плана для пользователя после назначения ему лицензии может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="4229d-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours, the user isn't assigned a Calling Plan pleaseContact support for business products - Admin Help.</span></span> <span data-ttu-id="4229d-113">Если по прошествии 24 часов пользователю не назначен план звонков, пожалуйста, выполните [Обращение в службу поддержки Office 365 для бизнеса: справка для администраторов](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="4229d-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="4229d-p104">**Сообщения об ошибках**. Если приобретено неправильное число лицензий, выдается сообщение об ошибке. Если требуется приобрести дополнительные лицензии на планы звонков, щелкните **Купить еще**.</span><span class="sxs-lookup"><span data-stu-id="4229d-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="4229d-116">**Дальнейшие действия**. После того, как вы назначили своим пользователям лицензии на тарифные планы, вам потребуется получить номера телефонов для вашей организации, а затем назначить эти номера сотрудникам.</span><span class="sxs-lookup"><span data-stu-id="4229d-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, seeSet up Calling Plans.</span></span> <span data-ttu-id="4229d-117">Пошаговые инструкции см. в статье [Настройка планов звонков](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="4229d-117">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="4229d-118">Назначение лицензии на телефонную систему и тарифный план одному пользователю</span><span class="sxs-lookup"><span data-stu-id="4229d-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="4229d-p106">Шаги совпадают с шагами при назначении лицензии на Office 365. См. раздел [Управление лицензиями Office 365 бизнес](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="4229d-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="4229d-121">Массовое назначение лицензий на телефонную систему и тарифный план</span><span class="sxs-lookup"><span data-stu-id="4229d-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="4229d-122">Установите **Помощник по входу в Microsoft Online Services для ИТ-специалистов, версия RTW**.</span><span class="sxs-lookup"><span data-stu-id="4229d-122">Download and install **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="4229d-123">Не установлен модуль?</span><span class="sxs-lookup"><span data-stu-id="4229d-123">Don't have the module installed?</span></span> <span data-ttu-id="4229d-124">Загрузите его со страницы [Помощника по входу в Microsoft Online Services для ИТ-специалистов, версия RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="4229d-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="4229d-125">Установите **модуль Windows Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="4229d-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="4229d-126">Не установлен модуль?</span><span class="sxs-lookup"><span data-stu-id="4229d-126">Don't have the module installed?</span></span> <span data-ttu-id="4229d-127">Перейдите в раздел [Управление Azure AD с помощью Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) для ознакомления с инструкцией по загрузки и синтаксисом командлета.</span><span class="sxs-lookup"><span data-stu-id="4229d-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="4229d-128">После установки модулей назначьте пользователям лицензии в командной строке Windows PowerShell, используя следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="4229d-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

  <span data-ttu-id="4229d-129">В этом примере **лицензия "Корпоративный E3"** назначается вместе с лицензией на **телефонную систему** и **план внутренних звонков**.</span><span class="sxs-lookup"><span data-stu-id="4229d-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

  <span data-ttu-id="4229d-130">Названия лицензий и наименования продуктов в сценарии выделены курсивом. См. раздел **Названия продуктов и номера SKU для телефонной системы и плана звонков, используемые для сценариев** после примера.</span><span class="sxs-lookup"><span data-stu-id="4229d-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="4229d-131">Названия продуктов и номера SKU для телефонной системы и плана звонков, использующиеся для сценариев</span><span class="sxs-lookup"><span data-stu-id="4229d-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="4229d-132">**Наименование товара**</span><span class="sxs-lookup"><span data-stu-id="4229d-132">**Product name**</span></span>|<span data-ttu-id="4229d-133">**Наименование товарной единицы**</span><span class="sxs-lookup"><span data-stu-id="4229d-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4229d-134">Корпоративный E5 (с телефонной системой)</span><span class="sxs-lookup"><span data-stu-id="4229d-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="4229d-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="4229d-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="4229d-136">Корпоративный E3</span><span class="sxs-lookup"><span data-stu-id="4229d-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="4229d-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="4229d-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="4229d-138">Корпоративный E1</span><span class="sxs-lookup"><span data-stu-id="4229d-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="4229d-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="4229d-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="4229d-140">Skype для бизнеса Online Standalone Plan 2</span><span class="sxs-lookup"><span data-stu-id="4229d-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="4229d-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="4229d-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="4229d-142">Телефонная система</span><span class="sxs-lookup"><span data-stu-id="4229d-142">Phone System</span></span>  <br/> |<span data-ttu-id="4229d-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="4229d-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="4229d-144">План международных звонков</span><span class="sxs-lookup"><span data-stu-id="4229d-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="4229d-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="4229d-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="4229d-146">План внутренних звонков</span><span class="sxs-lookup"><span data-stu-id="4229d-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="4229d-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="4229d-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="4229d-148">Кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="4229d-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="4229d-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="4229d-149">MCOPSTNPP</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="4229d-150">Аудиоконференция. Советы и сценарии для назначения лицензий</span><span class="sxs-lookup"><span data-stu-id="4229d-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="4229d-151">Что нужно знать перед назначением лицензий на аудиоконференцию</span><span class="sxs-lookup"><span data-stu-id="4229d-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="4229d-p109">**Сторонний поставщик аудиоконференций**. Если для пользователя уже настроено использование стороннего поставщика аудиоконференций, при назначении ему лицензии на **аудиоконференцию** поставщиком аудиоконференций автоматически назначается Майкрософт, но вы можете снова задать стороннего поставщика.</span><span class="sxs-lookup"><span data-stu-id="4229d-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="4229d-154">Дальнейшие действия. После назначения лицензий на **аудиоконференции** необходимо назначить поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="4229d-154">Next steps: After you assign **Audio Conferencing** licenses, you need to assign a audio conferencing provider. Do one of the following:</span></span> <span data-ttu-id="4229d-155">См. [Назначение Майкрософт в качестве поставщика услуг аудиоконференций].</span><span class="sxs-lookup"><span data-stu-id="4229d-155">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="4229d-156">Назначение лицензии на аудиоконференции одному пользователю</span><span class="sxs-lookup"><span data-stu-id="4229d-156">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="4229d-p111">Шаги совпадают с шагами при назначении лицензии на Office 365. См. раздел [Управление лицензиями Office 365 бизнес](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="4229d-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="4229d-159">Массовое назначение лицензий на аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="4229d-159">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="4229d-160">Скачайте и установите [Помощник по входу в Microsoft Online Services для ИТ-специалистов, версия RTW ](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="4229d-160">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="4229d-p112">Загрузите и установите **модуль Windows Azure Active Directory**. Инструкции по установке и синтаксис командлетов см. в разделе[Управление службой Azure AD с помощью Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="4229d-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="4229d-163">После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="4229d-163">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="4229d-164">Названия лицензий и наименования продуктов в сценарии выделены курсивом.</span><span class="sxs-lookup"><span data-stu-id="4229d-164">The name of the licenses or product names in the script are listed in italics text. See Dial-in conferencing product names or SKUs used for scripting for all of the product names.</span></span> <span data-ttu-id="4229d-165">Полный перечень названий продуктов см. в разделе [Названия продуктов и номера SKU для аудиоконференций, использующихся для сценариев](assign-skype-for-business-and-microsoft-teams-licenses.md#sku).</span><span class="sxs-lookup"><span data-stu-id="4229d-165">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="4229d-166">В этом примере лицензия "Корпоративный E3" назначается вместе с лицензией на аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="4229d-166">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="4229d-167">Названия продуктов и номера SKU для аудиоконференций, использующихся для сценариев</span><span class="sxs-lookup"><span data-stu-id="4229d-167">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="4229d-168"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="4229d-168"><a name="sku"> </a></span></span>

|<span data-ttu-id="4229d-169">**Наименование товара**</span><span class="sxs-lookup"><span data-stu-id="4229d-169">**Product name**</span></span>|<span data-ttu-id="4229d-170">**Наименование товарной единицы**</span><span class="sxs-lookup"><span data-stu-id="4229d-170">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4229d-171">Аудиоконференция</span><span class="sxs-lookup"><span data-stu-id="4229d-171">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="4229d-172">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="4229d-172">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="4229d-173">Skype для бизнеса Online Standalone Plan 2</span><span class="sxs-lookup"><span data-stu-id="4229d-173">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="4229d-174">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="4229d-174">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="4229d-175">Корпоративный E1</span><span class="sxs-lookup"><span data-stu-id="4229d-175">Enterprise E1</span></span>  <br/> |<span data-ttu-id="4229d-176">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="4229d-176">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="4229d-177">Корпоративный E3</span><span class="sxs-lookup"><span data-stu-id="4229d-177">Enterprise E3</span></span>  <br/> |<span data-ttu-id="4229d-178">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="4229d-178">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="4229d-179">Корпоративный E5 (без аудиоконференции)</span><span class="sxs-lookup"><span data-stu-id="4229d-179">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="4229d-180">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="4229d-180">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="4229d-181">Корпоративный E5 (с аудиоконференцией)</span><span class="sxs-lookup"><span data-stu-id="4229d-181">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="4229d-182">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="4229d-182">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="4229d-183">Кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="4229d-183">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="4229d-184">Что нужно знать перед назначением лицензий для кредитов на связь</span><span class="sxs-lookup"><span data-stu-id="4229d-184">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="4229d-185">**Клиенты плана "Корпоративный E5"**. Даже если вашим пользователям назначена лицензия на план "Корпоративный E5", рекомендуется назначить им лицензии на **кредиты на связь**.</span><span class="sxs-lookup"><span data-stu-id="4229d-185">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communication Credits** licenses.</span></span>
    
- <span data-ttu-id="4229d-186">**Дальнейшие действия**. После назначения этих лицензий вам потребуется получить номера телефонов для организации, а затем назначить их сотрудникам.</span><span class="sxs-lookup"><span data-stu-id="4229d-186">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, seeSet up Calling Plans.</span></span> <span data-ttu-id="4229d-187">Пошаговые инструкции см. в статье [Настройка планов звонков](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="4229d-187">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="4229d-188">Назначение лицензии на кредиты на связь одному пользователю</span><span class="sxs-lookup"><span data-stu-id="4229d-188">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="4229d-p115">Действия такие же, как и при назначении лицензии на Office 365. См. статью [Управление лицензиями Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="4229d-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="4229d-191">Массовое назначение лицензий на кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="4229d-191">How to assign Communication Credits licenses in bulk</span></span>

<span data-ttu-id="4229d-p116">Ознакомьтесь с примером сценария для назначения лицензий на **аудиоконференции**. Обновите его, указав сведения для назначения лицензий на **кредиты на связь**.</span><span class="sxs-lookup"><span data-stu-id="4229d-p116">Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4229d-194">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="4229d-194">Related topics</span></span>
  
[<span data-ttu-id="4229d-195">Настройка тарифных планов</span><span class="sxs-lookup"><span data-stu-id="4229d-195">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="4229d-196">Добавление средств и управление кредитами на связь</span><span class="sxs-lookup"><span data-stu-id="4229d-196">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
