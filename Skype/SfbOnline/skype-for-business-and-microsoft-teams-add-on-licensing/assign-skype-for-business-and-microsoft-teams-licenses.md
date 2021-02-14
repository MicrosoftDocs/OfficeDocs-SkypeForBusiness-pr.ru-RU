---
title: Назначение лицензий Skype для бизнеса
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: 'Узнайте, как назначить лицензии Skype для бизнеса на телефонные системы, аудиоконференции, планы звонков и кредиты на связь. '
ms.openlocfilehash: e17050c133643d44cd4811ddc5d70852f1ad50d5
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "44204850"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="dd827-103">Назначение лицензий Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="dd827-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="dd827-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span><span class="sxs-lookup"><span data-stu-id="dd827-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd827-106">Сведения о том, какие лицензии необходимо приобрести и как  их приобрести ,в зависимости от плана Microsoft 365 или Office 365 см. в лицензировании надстройки [Skype](skype-for-business-and-microsoft-teams-add-on-licensing.md) для бизнеса, чтобы пользователи могли получить аудиоконференцию, бесплатные номера и возможность звонить на телефонные номера за пределы вашей компании.</span><span class="sxs-lookup"><span data-stu-id="dd827-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Microsoft 365 or Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="dd827-107">Телефонные системы и планы звонков. Советы и сценарии по назначению лицензий</span><span class="sxs-lookup"><span data-stu-id="dd827-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="dd827-108">Что нужно знать перед назначением лицензий на аудиоконференцию, телефонную систему и план звонков</span><span class="sxs-lookup"><span data-stu-id="dd827-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="dd827-p102">**При использовании локальных подключений ТСОП для пользователей в гибридных средах** необходимо назначить только лицензию на **телефонную систему**. Назначать план звонков **НЕ НУЖНО**.</span><span class="sxs-lookup"><span data-stu-id="dd827-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="dd827-p103">**Задержка** после назначения лицензий: из-за задержки между Microsoft 365 или Office 365 и Skype для бизнеса Online назначение пользователю плана звонков после назначения лицензии может занять до 24 часов. Если по и после 24 часов пользователю не назначен план звонков, обратитесь в службу поддержки по продуктам для [бизнеса— справку для администраторов.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="dd827-p103">**Latency after assigning licenses**: Because of the latency between Microsoft 365 or Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="dd827-p104">**Сообщения об ошибках**. Если приобретено неправильное число лицензий, выдается сообщение об ошибке. Если требуется приобрести дополнительные лицензии на планы звонков, щелкните **Купить еще**.</span><span class="sxs-lookup"><span data-stu-id="dd827-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="dd827-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="dd827-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="dd827-118">Назначение лицензии на телефонную систему и план звонков одному пользователю</span><span class="sxs-lookup"><span data-stu-id="dd827-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="dd827-p106">Действия те же, что и при назначении лицензии на Microsoft 365 или Office 365. См. ["Назначение и удаление лицензий для Microsoft 365 для бизнеса".](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="dd827-p106">The steps are the same as assigning a Microsoft 365 or Office 365 license. See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="dd827-121">Массовое назначение лицензий на телефонную систему и план звонков</span><span class="sxs-lookup"><span data-stu-id="dd827-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="dd827-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span><span class="sxs-lookup"><span data-stu-id="dd827-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="dd827-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span><span class="sxs-lookup"><span data-stu-id="dd827-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="dd827-128">После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="dd827-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="dd827-129">В этом примере **лицензия "Корпоративный E3"** назначается вместе с лицензией на **телефонную систему** и **план внутренних звонков**.</span><span class="sxs-lookup"><span data-stu-id="dd827-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="dd827-130">Названия лицензий и наименования продуктов в сценарии выделены курсивом. См. раздел **Названия продуктов и номера SKU для телефонной системы и плана звонков, используемые для сценариев** после примера.</span><span class="sxs-lookup"><span data-stu-id="dd827-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="dd827-131">Названия продуктов и номера SKU для телефонной системы и плана звонков, использующиеся для сценариев</span><span class="sxs-lookup"><span data-stu-id="dd827-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="dd827-132">**Наименование товара**</span><span class="sxs-lookup"><span data-stu-id="dd827-132">**Product name**</span></span>|<span data-ttu-id="dd827-133">**Наименование товарной единицы**</span><span class="sxs-lookup"><span data-stu-id="dd827-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dd827-134">Корпоративный E5 (с телефонной системой)</span><span class="sxs-lookup"><span data-stu-id="dd827-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="dd827-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="dd827-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="dd827-136">Корпоративный E3</span><span class="sxs-lookup"><span data-stu-id="dd827-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="dd827-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="dd827-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="dd827-138">Корпоративный E1</span><span class="sxs-lookup"><span data-stu-id="dd827-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="dd827-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="dd827-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="dd827-140">Skype для бизнеса Online Standalone Plan 2</span><span class="sxs-lookup"><span data-stu-id="dd827-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="dd827-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="dd827-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="dd827-142">Телефонная система</span><span class="sxs-lookup"><span data-stu-id="dd827-142">Phone System</span></span>  <br/> |<span data-ttu-id="dd827-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="dd827-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="dd827-144">План международных звонков</span><span class="sxs-lookup"><span data-stu-id="dd827-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="dd827-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="dd827-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="dd827-146">План внутренних звонков (планы: 3000 мин США/1200 мин ЕС)</span><span class="sxs-lookup"><span data-stu-id="dd827-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="dd827-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="dd827-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="dd827-148">План внутренних звонков (план звонков: 120 мин)</span><span class="sxs-lookup"><span data-stu-id="dd827-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="dd827-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="dd827-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="dd827-150">План внутренних звонков (план звонков: 240 мин)</span><span class="sxs-lookup"><span data-stu-id="dd827-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="dd827-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="dd827-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="dd827-152">Кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="dd827-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="dd827-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="dd827-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="dd827-154">Аудиоконференция. Советы и сценарии для назначения лицензий</span><span class="sxs-lookup"><span data-stu-id="dd827-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="dd827-155">Что нужно знать перед назначением лицензий на аудиоконференцию</span><span class="sxs-lookup"><span data-stu-id="dd827-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="dd827-p109">**Сторонний поставщик аудиоконференций**. Если для пользователя уже настроено использование стороннего поставщика аудиоконференций, при назначении ему лицензии на **аудиоконференцию** поставщиком аудиоконференций автоматически назначается Майкрософт, но вы можете снова задать стороннего поставщика.</span><span class="sxs-lookup"><span data-stu-id="dd827-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="dd827-158">Дальнейшие действия. После  назначения лицензий на аудиоконференцию необходимо назначить поставщика услуг аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="dd827-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="dd827-159">См. [Назначение Майкрософт в качестве поставщика услуг аудиоконференций].</span><span class="sxs-lookup"><span data-stu-id="dd827-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="dd827-160">Назначение лицензии на аудиоконференции одному пользователю</span><span class="sxs-lookup"><span data-stu-id="dd827-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="dd827-161">Действия те же, что и при назначении лицензии на Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="dd827-161">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="dd827-162">См. ["Назначение и удаление лицензий для Microsoft 365 для бизнеса".](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="dd827-162">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="dd827-163">Массовое назначение лицензий на аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="dd827-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="dd827-164">Скачайте и установите [Помощник по входу в Microsoft Online Services для ИТ-специалистов, версия RTW ](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="dd827-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="dd827-p112">Загрузите и установите **модуль Windows Azure Active Directory**. Инструкции по установке и синтаксис командлетов см. в разделе [Управление службой Azure AD с помощью Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="dd827-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="dd827-167">После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="dd827-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="dd827-168">Названия лицензий и наименования продуктов в сценарии указаны в тексте, который содержится в виде шрифта.</span><span class="sxs-lookup"><span data-stu-id="dd827-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="dd827-169">Полный перечень названий продуктов см. в разделе [Названия продуктов и номера SKU для аудиоконференций, использующихся для сценариев](assign-skype-for-business-and-microsoft-teams-licenses.md#sku).</span><span class="sxs-lookup"><span data-stu-id="dd827-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="dd827-170">В этом примере лицензия "Корпоративный E3" назначается вместе с лицензией на аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="dd827-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

    ```powershell
    #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="dd827-171">Названия продуктов и номера SKU для аудиоконференций, использующихся для сценариев</span><span class="sxs-lookup"><span data-stu-id="dd827-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="dd827-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="dd827-172"><a name="sku"> </a></span></span>

|<span data-ttu-id="dd827-173">**Наименование товара**</span><span class="sxs-lookup"><span data-stu-id="dd827-173">**Product name**</span></span>|<span data-ttu-id="dd827-174">**Наименование товарной единицы**</span><span class="sxs-lookup"><span data-stu-id="dd827-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dd827-175">Аудиоконференция</span><span class="sxs-lookup"><span data-stu-id="dd827-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="dd827-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="dd827-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="dd827-177">Skype для бизнеса Online Standalone Plan 2</span><span class="sxs-lookup"><span data-stu-id="dd827-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="dd827-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="dd827-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="dd827-179">Корпоративный E1</span><span class="sxs-lookup"><span data-stu-id="dd827-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="dd827-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="dd827-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="dd827-181">Корпоративный E3</span><span class="sxs-lookup"><span data-stu-id="dd827-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="dd827-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="dd827-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="dd827-183">Корпоративный E5 (без аудиоконференции)</span><span class="sxs-lookup"><span data-stu-id="dd827-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="dd827-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="dd827-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="dd827-185">Корпоративный E5 (с аудиоконференцией)</span><span class="sxs-lookup"><span data-stu-id="dd827-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="dd827-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="dd827-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="dd827-187">Кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="dd827-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="dd827-188">Что нужно знать перед назначением лицензий на кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="dd827-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="dd827-189">**Корпоративные клиенты E5.** Даже если вашим пользователям назначены лицензии на корпоративный E5, мы по-прежнему рекомендуем назначать им лицензии на кредиты **на** связь.</span><span class="sxs-lookup"><span data-stu-id="dd827-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="dd827-190">**Дальнейшие действия.** После назначения этих лицензий вам потребуется получить номера телефонов для организации, а затем назначить их людям в организации.</span><span class="sxs-lookup"><span data-stu-id="dd827-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="dd827-191">Пошаговые инструкции см. в статье [Настройка планов звонков](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="dd827-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="dd827-192">Назначение лицензии на кредиты на связь одному пользователю</span><span class="sxs-lookup"><span data-stu-id="dd827-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="dd827-193">Действия те же, что и при назначении лицензии на Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="dd827-193">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="dd827-194">См. ["Назначение и удаление лицензий для Microsoft 365 для бизнеса".](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="dd827-194">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="dd827-195">Массовое назначение лицензий на кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="dd827-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="dd827-196">Ознакомьтесь с примером сценария для назначения лицензий на **аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="dd827-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="dd827-197">Обновите сведения для назначения лицензий на **кредиты на связь**.</span><span class="sxs-lookup"><span data-stu-id="dd827-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dd827-198">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="dd827-198">Related topics</span></span>
  
[<span data-ttu-id="dd827-199">Настройка планов звонков</span><span class="sxs-lookup"><span data-stu-id="dd827-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="dd827-200">Пополнение средств и управление кредитами на связь</span><span class="sxs-lookup"><span data-stu-id="dd827-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
