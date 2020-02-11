---
title: Назначение лицензий Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Сведения о назначении лицензий для таких функций, как голосовая конференция, телефонная система и планы звонков.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46ae5952d79f3f0ef0a6137b240661550ecead00
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888688"
---
# <a name="assign-microsoft-teams-licenses"></a><span data-ttu-id="44ed4-103">Назначение лицензий Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="44ed4-103">Assign Microsoft Teams licenses</span></span>

<span data-ttu-id="44ed4-104">Вы можете назначать лицензии пользователям для таких функций, как голосовая конференция, телефонная система и планы звонков.</span><span class="sxs-lookup"><span data-stu-id="44ed4-104">You can assign licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="44ed4-105">В этой статье объясняется, как добавить эти лицензии в массовый и для отдельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="44ed4-105">This article explains how to add these licenses in bulk and for an individual user.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="44ed4-106">Сведения о лицензиях на [надстройки Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) , которые нужно приобрести, и о том, как их приобрести, в зависимости от вашего плана Office 365, чтобы пользователи могли получать видеоконференции, бесплатные номера и возможность звонить на телефонные номера за пределами вашего бизнеса.</span><span class="sxs-lookup"><span data-stu-id="44ed4-106">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and how to buy them, depending on your Office 365 plan, so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="44ed4-107">Телефонные системы и планы звонков. Советы и сценарии по назначению лицензий</span><span class="sxs-lookup"><span data-stu-id="44ed4-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="44ed4-108">Ниже приведены сведения, которые необходимо знать перед назначением лицензий на голосовую конференцию, телефонную систему и план звонков.</span><span class="sxs-lookup"><span data-stu-id="44ed4-108">Here’s what you need to know before assigning Audio Conferencing, Phone System, and Calling Plan licenses.</span></span>

- <span data-ttu-id="44ed4-109">**Используете локальную сеть PSTN для гибридных пользователей?**</span><span class="sxs-lookup"><span data-stu-id="44ed4-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="44ed4-110">Если да, вам нужно назначить лицензию на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="44ed4-110">If so, you only need to assign a Phone System license.</span></span> <span data-ttu-id="44ed4-111">НЕ следует назначать план звонков.</span><span class="sxs-lookup"><span data-stu-id="44ed4-111">You should NOT assign a Calling Plan.</span></span>

- <span data-ttu-id="44ed4-112">**Задержка после назначения лицензий**. из-за задержки между Office 365 и Microsoft Teams для назначения абоненту плана после назначения лицензии может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="44ed4-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="44ed4-113">Если по истечении 24 часов пользователь не назначил план звонков, [обратитесь в службу поддержки для бизнес-продуктов — Справка для администраторов](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="44ed4-113">If after 24 hours the user isn't assigned a Calling Plan, please [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="44ed4-p104">**Сообщения об ошибках**. Если приобретено неправильное число лицензий, выдается сообщение об ошибке. Если требуется приобрести дополнительные лицензии на планы звонков, щелкните **Купить еще**.</span><span class="sxs-lookup"><span data-stu-id="44ed4-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>

- <span data-ttu-id="44ed4-116">**Дальнейшие действия**: после назначения пользователям лицензий на план звонков вам потребуется получить номера телефонов для своей организации, а затем назначить эти номера сотрудникам Организации.</span><span class="sxs-lookup"><span data-stu-id="44ed4-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="44ed4-117">Пошаговые инструкции см. в статье [Настройка планов звонков](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="44ed4-117">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="44ed4-118">Назначение лицензии на телефонную систему и план звонков для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="44ed4-118">Assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="44ed4-119">Эти действия такие же, как назначение лицензии на Office 365.</span><span class="sxs-lookup"><span data-stu-id="44ed4-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="44ed4-120">Ознакомьтесь с [Разназначением и удалением лицензий для Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="44ed4-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="44ed4-121">Массовое Назначение лицензий на телефонную систему и план звонков</span><span class="sxs-lookup"><span data-stu-id="44ed4-121">Assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="44ed4-122">Установка помощника по входу в Microsoft Online Services для ИТ-специалистов RTW.</span><span class="sxs-lookup"><span data-stu-id="44ed4-122">Install the Microsoft Online Services Sign-In Assistant for IT Professionals RTW.</span></span> <span data-ttu-id="44ed4-123">Не установлен модуль?</span><span class="sxs-lookup"><span data-stu-id="44ed4-123">Don't have the module installed?</span></span> <span data-ttu-id="44ed4-124">Загрузите его со страницы [Помощника по входу в Microsoft Online Services для ИТ-специалистов, версия RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="44ed4-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="44ed4-125">Установите модуль Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="44ed4-125">Install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="44ed4-126">Не установлен модуль?</span><span class="sxs-lookup"><span data-stu-id="44ed4-126">Don't have the module installed?</span></span> <span data-ttu-id="44ed4-127">Перейдите в раздел [Управление Azure AD с помощью Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) для ознакомления с инструкцией по загрузки и синтаксисом командлета.</span><span class="sxs-lookup"><span data-stu-id="44ed4-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="44ed4-128">После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="44ed4-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="44ed4-129">В этом примере лицензия "Корпоративный E3" назначается вместе с лицензией на телефонную систему и план внутренних звонков.</span><span class="sxs-lookup"><span data-stu-id="44ed4-129">This example assigns an Enterprise E3 license along with a Phone System and a Domestic Calling Plan license.</span></span>

<span data-ttu-id="44ed4-130">Названия лицензий и названий продуктов в сценарии выводятся курсивом (в этом примере [используются названия продуктов и номера SKU, используемые для создания сценариев, в телефонной системе и в планах звонков](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting)).</span><span class="sxs-lookup"><span data-stu-id="44ed4-130">The name of the licenses or product names in the script are listed in italics (see [Phone System and Calling Plans product names or SKUs used for scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), after the example).</span></span>

```powershell
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

## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="44ed4-131">Названия продуктов и номера SKU для телефонной системы и плана звонков, использующиеся для сценариев</span><span class="sxs-lookup"><span data-stu-id="44ed4-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

| <span data-ttu-id="44ed4-132">Наименование товара</span><span class="sxs-lookup"><span data-stu-id="44ed4-132">Product name</span></span> | <span data-ttu-id="44ed4-133">Наименование товарной единицы</span><span class="sxs-lookup"><span data-stu-id="44ed4-133">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="44ed4-134">Корпоративный E5 (с телефонной системой)</span><span class="sxs-lookup"><span data-stu-id="44ed4-134">Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="44ed4-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="44ed4-135">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="44ed4-136">Корпоративный E3</span><span class="sxs-lookup"><span data-stu-id="44ed4-136">Enterprise E3</span></span> | <span data-ttu-id="44ed4-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="44ed4-137">ENTERPRISEPACK</span></span> | 
| <span data-ttu-id="44ed4-138">Корпоративный E1</span><span class="sxs-lookup"><span data-stu-id="44ed4-138">Enterprise E1</span></span> | <span data-ttu-id="44ed4-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="44ed4-139">STANDARDPACK</span></span> | 
| <span data-ttu-id="44ed4-140">Телефонная система</span><span class="sxs-lookup"><span data-stu-id="44ed4-140">Phone System</span></span> | <span data-ttu-id="44ed4-141">MCOEV</span><span class="sxs-lookup"><span data-stu-id="44ed4-141">MCOEV</span></span> |
| <span data-ttu-id="44ed4-142">План международных звонков на внутренние &</span><span class="sxs-lookup"><span data-stu-id="44ed4-142">Domestic & International Calling Plan</span></span> | <span data-ttu-id="44ed4-143">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="44ed4-143">MCOPSTN2</span></span> |
| <span data-ttu-id="44ed4-144">План внутренних вызовов (3000 минут на пользователя/месяц для US/PR/CA, 1200 минут на пользователя/месяц для стран ЕС)</span><span class="sxs-lookup"><span data-stu-id="44ed4-144">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="44ed4-145">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="44ed4-145">MCOPSTN1</span></span> |
| <span data-ttu-id="44ed4-146">План внутренних вызовов (120 минут на пользователя/месяц для каждой страны)</span><span class="sxs-lookup"><span data-stu-id="44ed4-146">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="44ed4-147">*Примечание. Этот план недоступен в США*.</span><span class="sxs-lookup"><span data-stu-id="44ed4-147">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="44ed4-148">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="44ed4-148">MCOPSTN5</span></span> |
| <span data-ttu-id="44ed4-149">План внутренних вызовов (240 минут на пользователя/месяц для каждой страны)</span><span class="sxs-lookup"><span data-stu-id="44ed4-149">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="44ed4-150">*Примечание. Этот план недоступен в США*.</span><span class="sxs-lookup"><span data-stu-id="44ed4-150">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="44ed4-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="44ed4-151">MCOPSTN6</span></span> |
| <span data-ttu-id="44ed4-152">Кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="44ed4-152">Communications Credits</span></span> | <span data-ttu-id="44ed4-153">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="44ed4-153">MCOPSTNPP</span></span> | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="44ed4-154">Аудио-конференции: советы и сценарии для назначения лицензий</span><span class="sxs-lookup"><span data-stu-id="44ed4-154">Audio Conferencing: tips and scripts for assigning licenses</span></span>

<span data-ttu-id="44ed4-155">Ниже приведены сведения, которые необходимо знать перед назначением лицензий на голосовую конференцию.</span><span class="sxs-lookup"><span data-stu-id="44ed4-155">Here's what you need to know before assigning Audio Conferencing licenses.</span></span>

- <span data-ttu-id="44ed4-156">**Сторонние поставщики видеоконференций**: если кто-то уже настроен на использование стороннего поставщика видеоконференций, при назначении лицензии на голосовую конференцию, она будет изменена на использование Microsoft в качестве поставщика голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="44ed4-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an Audio Conferencing license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="44ed4-157">Если для пользователя уже настроено использование стороннего поставщика аудиоконференций, при назначении ему лицензии на аудиоконференцию поставщиком аудиоконференций автоматически назначается Майкрософт, но вы можете снова задать стороннего поставщика.</span><span class="sxs-lookup"><span data-stu-id="44ed4-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="44ed4-158">**Дальнейшие действия**: после назначения лицензий на голосовую конференцию необходимо назначить поставщика услуг голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="44ed4-158">**Next steps**: After you assign Audio Conferencing licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="44ed4-159">[В разделе Назначение Microsoft в качестве поставщика звуковых конференций](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="44ed4-159">See [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

## <a name="assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="44ed4-160">Назначение лицензии на голосовую конференцию для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="44ed4-160">Assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="44ed4-161">Эти действия такие же, как назначение лицензии на Office 365.</span><span class="sxs-lookup"><span data-stu-id="44ed4-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="44ed4-162">Ознакомьтесь с [Разназначением и удалением лицензий для Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="44ed4-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="44ed4-163">Массовое Назначение лицензий на голосовую конференцию</span><span class="sxs-lookup"><span data-stu-id="44ed4-163">Assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="44ed4-164">Скачайте и установите [Помощник по входу в Microsoft Online Services для ИТ-специалистов, версия RTW ](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="44ed4-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="44ed4-165">Скачайте и установите модуль Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="44ed4-165">Download and install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="44ed4-166">Перейдите в раздел [Управление Azure AD с помощью Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) для ознакомления с инструкцией по загрузки и синтаксисом командлета.</span><span class="sxs-lookup"><span data-stu-id="44ed4-166">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

<span data-ttu-id="44ed4-167">После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="44ed4-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="44ed4-168">Названия лицензий и названий продуктов в сценарии выводятся курсивом.</span><span class="sxs-lookup"><span data-stu-id="44ed4-168">The name of the licenses or product names in the script are listed in italics.</span></span> <span data-ttu-id="44ed4-169">Посмотрите [названия продуктов и SKU для голосовой связи, которые используются для создания сценариев](#audio-conferencing-product-names-or-skus-used-for-scripting) для всех названий продуктов.</span><span class="sxs-lookup"><span data-stu-id="44ed4-169">See [Audio Conferencing product names or SKUS used for scripting](#audio-conferencing-product-names-or-skus-used-for-scripting) for all of the product names.</span></span>

<span data-ttu-id="44ed4-170">В этом примере лицензия "Корпоративный E3" назначается вместе с лицензией на аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="44ed4-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

```powershell
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

## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="44ed4-171">Названия и номера продуктов для голосовой конференции, используемые для создания сценариев</span><span class="sxs-lookup"><span data-stu-id="44ed4-171">Audio Conferencing product names or SKUS used for scripting</span></span>

| <span data-ttu-id="44ed4-172">Наименование товара</span><span class="sxs-lookup"><span data-stu-id="44ed4-172">Product name</span></span> | <span data-ttu-id="44ed4-173">Наименование товарной единицы</span><span class="sxs-lookup"><span data-stu-id="44ed4-173">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="44ed4-174">Голосовая конференция (подписка)</span><span class="sxs-lookup"><span data-stu-id="44ed4-174">Audio Conferencing (subscription)</span></span> | <span data-ttu-id="44ed4-175">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="44ed4-175">MCOMEETADV</span></span> | 
| <span data-ttu-id="44ed4-176">Оплата для голосовой конференции за минуту (оплата за один звонок)</span><span class="sxs-lookup"><span data-stu-id="44ed4-176">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="44ed4-177">*Примечание. требует настройки и включения кредитов на связь*.</span><span class="sxs-lookup"><span data-stu-id="44ed4-177">*Note: Requires Communications Credits to be set up and enabled*.</span></span> | <span data-ttu-id="44ed4-178">мкомитакпеа</span><span class="sxs-lookup"><span data-stu-id="44ed4-178">MCOMEETACPEA</span></span> |
| <span data-ttu-id="44ed4-179">Корпоративный E1</span><span class="sxs-lookup"><span data-stu-id="44ed4-179">Enterprise E1</span></span> | <span data-ttu-id="44ed4-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="44ed4-180">STANDARDPACK</span></span> | 
| <span data-ttu-id="44ed4-181">Корпоративный E3</span><span class="sxs-lookup"><span data-stu-id="44ed4-181">Enterprise E3</span></span> | <span data-ttu-id="44ed4-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="44ed4-182">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="44ed4-183">Корпоративный E5 (без аудиоконференции)</span><span class="sxs-lookup"><span data-stu-id="44ed4-183">Enterprise E5 (without Audio Conferencing)</span></span> |  <span data-ttu-id="44ed4-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="44ed4-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="44ed4-185">Корпоративный E5 (с аудиоконференцией)</span><span class="sxs-lookup"><span data-stu-id="44ed4-185">Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="44ed4-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="44ed4-186">ENTERPRISEPREMIUM</span></span> |

##  <a name="communications-credits"></a><span data-ttu-id="44ed4-187">Кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="44ed4-187">Communications Credits</span></span>

<span data-ttu-id="44ed4-188">Вот что нужно знать перед назначением лицензий на кредиты на связь.</span><span class="sxs-lookup"><span data-stu-id="44ed4-188">Here's what you need to know before assigning Communications Credits licenses.</span></span>

- <span data-ttu-id="44ed4-189">**Клиенты с корпоративным**энергообщением: даже если вашим пользователям назначены лицензии на ресурсы в корпоративной среде, мы по-прежнему рекомендуем назначать им лицензии на передачу данных.</span><span class="sxs-lookup"><span data-stu-id="44ed4-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them Communications Credits licenses.</span></span>

- <span data-ttu-id="44ed4-190">**Дальнейшие действия**: после назначения этих лицензий вам потребуется получить номера телефонов для своей организации, а затем назначить эти номера сотрудникам Организации.</span><span class="sxs-lookup"><span data-stu-id="44ed4-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="44ed4-191">Пошаговые инструкции см. в статье [Настройка планов звонков](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="44ed4-191">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="44ed4-192">Назначение лицензии на пересылаемые баллы для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="44ed4-192">Assign a Communications Credits license to one user</span></span>

<span data-ttu-id="44ed4-193">Эти действия такие же, как назначение лицензии на Office 365.</span><span class="sxs-lookup"><span data-stu-id="44ed4-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="44ed4-194">Ознакомьтесь с [Разназначением и удалением лицензий для Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="44ed4-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="44ed4-195">Массовое Назначение лицензий на кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="44ed4-195">Assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="44ed4-196">Ознакомьтесь с примером сценария для назначения лицензий на аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="44ed4-196">Take a look at the sample script for assigning Audio Conferencing licenses.</span></span> <span data-ttu-id="44ed4-197">Обновите сведения для назначения лицензий на кредиты на связь.</span><span class="sxs-lookup"><span data-stu-id="44ed4-197">Update it with the info for assigning Communications Credits licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="44ed4-198">См. также</span><span class="sxs-lookup"><span data-stu-id="44ed4-198">Related topics</span></span>

[<span data-ttu-id="44ed4-199">Настройка планов звонков</span><span class="sxs-lookup"><span data-stu-id="44ed4-199">Set up Calling Plans</span></span>](set-up-calling-plans.md)
</br>
[<span data-ttu-id="44ed4-200">Пополнение средств и управление кредитами на связь</span><span class="sxs-lookup"><span data-stu-id="44ed4-200">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
