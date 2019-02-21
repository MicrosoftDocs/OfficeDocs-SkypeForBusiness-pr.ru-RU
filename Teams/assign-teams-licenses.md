---
title: Назначение лицензий групп
author: lolaj
ms.author: lolaj
manager: serdars
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: mikedav
description: Узнайте, как для назначения лицензий для функции, такие как аудио конференц-связи, телефонной системой и планы вызова.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 078db13179f0e33cb950c00ea58e76f11c8eb405
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2019
ms.locfileid: "30127632"
---
# <a name="assign-microsoft-teams-licenses"></a><span data-ttu-id="5d7cd-103">Назначение лицензий группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5d7cd-103">Assign Microsoft Teams licenses</span></span>

<span data-ttu-id="5d7cd-104">Можно назначить лицензий пользователей для таких функций, как аудиоконференции, телефонной системой и вызов планов.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-104">You can assign licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="5d7cd-105">В этой статье объясняется, как добавить эти лицензии в пакетном режиме, а также для отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-105">This article explains how to add these licenses in bulk and for an individual user.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="5d7cd-106">[Лицензирование дополнительный компонент группами Майкрософт](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) сведения о см что планирование лицензий, которые необходимо приобрести и как приобрести их, в зависимости от Office 365, так что пользователи получают аудиоконференции, обслуживание бесплатных номеров и возможность вызова телефонных номеров за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-106">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and how to buy them, depending on your Office 365 plan, so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="5d7cd-107">Телефонные системы и планы звонков. Советы и сценарии по назначению лицензий</span><span class="sxs-lookup"><span data-stu-id="5d7cd-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="5d7cd-108">Вот что нужно знать, прежде чем назначения лицензий аудиоконференции, телефонной системой и вызов планирование.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-108">Here’s what you need to know before assigning Audio Conferencing, Phone System, and Calling Plan licenses.</span></span>

- <span data-ttu-id="5d7cd-109">**С помощью локального подключения к ТСОП для гибридных пользователей?**</span><span class="sxs-lookup"><span data-stu-id="5d7cd-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="5d7cd-110">Если Да, необходимо назначить лицензию телефонной системой.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-110">If so, you only need to assign a Phone System license.</span></span> <span data-ttu-id="5d7cd-111">НЕ следует назначить вызов планирование.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-111">You should NOT assign a Calling Plan.</span></span>

- <span data-ttu-id="5d7cd-112">**Задержка после назначения лицензий**: из-за задержки между Office 365 и группами Майкрософт, может потребоваться до 24 часов для пользователя, чтобы назначить вызов планирование после назначении лицензии.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="5d7cd-113">Если после 24 часов пользователя не будет назначен вызов планирование, пожалуйста, [обратитесь в службу поддержки продуктов бизнес - admin справки](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="5d7cd-113">If after 24 hours the user isn't assigned a Calling Plan, please [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="5d7cd-p104">**Сообщения об ошибках**. Если приобретено неправильное число лицензий, выдается сообщение об ошибке. Если требуется приобрести дополнительные лицензии на планы звонков, щелкните **Купить еще**.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>

- <span data-ttu-id="5d7cd-116">**Дальнейшие действия**: после назначения лицензий на вызов планирование для пользователей, необходимо получить номера телефонов для вашей организации, а затем назначить эти номера для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="5d7cd-117">Пошаговые инструкции см. в статье [Настройка планов звонков](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="5d7cd-117">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="5d7cd-118">Назначить телефонной системой и вызов планирование лицензию для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="5d7cd-118">Assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="5d7cd-119">Действия такие же, как назначение лицензии Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="5d7cd-120">Просмотрите [Назначение и удаление лицензий на Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="5d7cd-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="5d7cd-121">Назначение лицензий телефонной системой и вызов планирование в пакетном режиме</span><span class="sxs-lookup"><span data-stu-id="5d7cd-121">Assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="5d7cd-122">Установка Microsoft Online Services помощник по входу для ИТ-специалистов RTW.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-122">Install the Microsoft Online Services Sign-In Assistant for IT Professionals RTW.</span></span> <span data-ttu-id="5d7cd-123">Не установлен модуль?</span><span class="sxs-lookup"><span data-stu-id="5d7cd-123">Don't have the module installed?</span></span> <span data-ttu-id="5d7cd-124">Загрузите его со страницы [Помощника по входу в Microsoft Online Services для ИТ-специалистов, версия RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="5d7cd-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="5d7cd-125">Установите модуль Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-125">Install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="5d7cd-126">Не установлен модуль?</span><span class="sxs-lookup"><span data-stu-id="5d7cd-126">Don't have the module installed?</span></span> <span data-ttu-id="5d7cd-127">Перейдите в раздел [Управление Azure AD с помощью Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) для ознакомления с инструкцией по загрузки и синтаксисом командлета.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="5d7cd-128">После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="5d7cd-129">В этом примере лицензия "Корпоративный E3" назначается вместе с лицензией на телефонную систему и план внутренних звонков.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-129">This example assigns an Enterprise E3 license along with a Phone System and a Domestic Calling Plan license.</span></span>

<span data-ttu-id="5d7cd-130">Имя лицензии или названия продуктов в скрипте, перечислены в курсив (см [телефонной системой и вызов планы названия продуктов или номера SKU, используемые для выполнения сценариев](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), после примера).</span><span class="sxs-lookup"><span data-stu-id="5d7cd-130">The name of the licenses or product names in the script are listed in italics (see [Phone System and Calling Plans product names or SKUs used for scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), after the example).</span></span>

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
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="5d7cd-131">Названия продуктов и номера SKU для телефонной системы и плана звонков, использующиеся для сценариев</span><span class="sxs-lookup"><span data-stu-id="5d7cd-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

| <span data-ttu-id="5d7cd-132">Наименование товара</span><span class="sxs-lookup"><span data-stu-id="5d7cd-132">Product name</span></span> | <span data-ttu-id="5d7cd-133">Наименование товарной единицы</span><span class="sxs-lookup"><span data-stu-id="5d7cd-133">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="5d7cd-134">Корпоративный E5 (с телефонной системой)</span><span class="sxs-lookup"><span data-stu-id="5d7cd-134">Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="5d7cd-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="5d7cd-135">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="5d7cd-136">Корпоративный E3</span><span class="sxs-lookup"><span data-stu-id="5d7cd-136">Enterprise E3</span></span> | <span data-ttu-id="5d7cd-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="5d7cd-137">ENTERPRISEPACK</span></span> | 
| <span data-ttu-id="5d7cd-138">Корпоративный E1</span><span class="sxs-lookup"><span data-stu-id="5d7cd-138">Enterprise E1</span></span> | <span data-ttu-id="5d7cd-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="5d7cd-139">STANDARDPACK</span></span> | 
| <span data-ttu-id="5d7cd-140">Телефонная система</span><span class="sxs-lookup"><span data-stu-id="5d7cd-140">Phone System</span></span> | <span data-ttu-id="5d7cd-141">MCOEV</span><span class="sxs-lookup"><span data-stu-id="5d7cd-141">MCOEV</span></span> |
| <span data-ttu-id="5d7cd-142">Планирование международных звонков внутри страны &</span><span class="sxs-lookup"><span data-stu-id="5d7cd-142">Domestic & International Calling Plan</span></span> | <span data-ttu-id="5d7cd-143">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="5d7cd-143">MCOPSTN2</span></span> |
| <span data-ttu-id="5d7cd-144">Внутренний вызов планирование (3000 минут на пользователя в месяц для США/связей с Общественностью/центра сертификации, 1200 минут в месяц пользователя для стран ЕС)</span><span class="sxs-lookup"><span data-stu-id="5d7cd-144">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="5d7cd-145">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="5d7cd-145">MCOPSTN1</span></span> |
| <span data-ttu-id="5d7cd-146">Внутренний вызов планирование (120 минут в месяц пользователя для каждой страны)</span><span class="sxs-lookup"><span data-stu-id="5d7cd-146">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="5d7cd-147">*Примечание: этот план не доступен в США*.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-147">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="5d7cd-148">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="5d7cd-148">MCOPSTN5</span></span> |
| <span data-ttu-id="5d7cd-149">Внутренний вызов планирование (240 минут в месяц пользователя для каждой страны)</span><span class="sxs-lookup"><span data-stu-id="5d7cd-149">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="5d7cd-150">*Примечание: этот план не доступен в США*.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-150">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="5d7cd-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="5d7cd-151">MCOPSTN6</span></span> |
| <span data-ttu-id="5d7cd-152">Кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="5d7cd-152">Communications Credits</span></span> | <span data-ttu-id="5d7cd-153">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="5d7cd-153">MCOPSTNPP</span></span> | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="5d7cd-154">Конференции: советы и сценарии для назначения лицензий</span><span class="sxs-lookup"><span data-stu-id="5d7cd-154">Audio Conferencing: tips and scripts for assigning licenses</span></span>

<span data-ttu-id="5d7cd-155">Вот что нужно знать, прежде чем назначения лицензий звук конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-155">Here's what you need to know before assigning Audio Conferencing licenses.</span></span>

- <span data-ttu-id="5d7cd-156">**Стороннего поставщика аудиоконференций**: Если кто-то уже настроен на использование поставщика аудиоконференций сторонних производителей, при их назначения лицензию на аудиоконференции, они будут изменены для использования Microsoft в качестве поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an Audio Conferencing license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="5d7cd-157">Если для пользователя уже настроено использование стороннего поставщика аудиоконференций, при назначении ему лицензии на аудиоконференцию поставщиком аудиоконференций автоматически назначается Майкрософт, но вы можете снова задать стороннего поставщика.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="5d7cd-158">**Дальнейшие действия**: после назначения лицензий аудиоконференций, им необходимо назначить поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-158">**Next steps**: After you assign Audio Conferencing licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="5d7cd-159">В разделе [Назначение Microsoft в качестве поставщика аудиоконференций](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="5d7cd-159">See [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

## <a name="assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="5d7cd-160">Назначение лицензии на аудиоконференции для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="5d7cd-160">Assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="5d7cd-161">Действия такие же, как назначение лицензии Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="5d7cd-162">Просмотрите [Назначение и удаление лицензий на Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="5d7cd-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="5d7cd-163">Назначение лицензий аудиоконференции в пакетном режиме</span><span class="sxs-lookup"><span data-stu-id="5d7cd-163">Assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="5d7cd-164">Скачайте и установите [Помощник по входу в Microsoft Online Services для ИТ-специалистов, версия RTW ](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="5d7cd-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="5d7cd-165">Загрузите и установите модуль Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-165">Download and install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="5d7cd-166">Перейдите в раздел [Управление Azure AD с помощью Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) для ознакомления с инструкцией по загрузки и синтаксисом командлета.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-166">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

<span data-ttu-id="5d7cd-167">После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="5d7cd-168">Имя лицензии или названия продуктов в скрипте, перечислены в курсив.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-168">The name of the licenses or product names in the script are listed in italics.</span></span> <span data-ttu-id="5d7cd-169">В разделе [имена аудиоконференции продукта или номера SKU, используемый для скриптов](#audio-conferencing-product-names-or-skus-used-for-scripting) для всех названия продуктов.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-169">See [Audio Conferencing product names or SKUS used for scripting](#audio-conferencing-product-names-or-skus-used-for-scripting) for all of the product names.</span></span>

<span data-ttu-id="5d7cd-170">В этом примере лицензия "Корпоративный E3" назначается вместе с лицензией на аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="5d7cd-171">Названия продуктов звукового конференц-связи или номера SKU, используемый для скриптов</span><span class="sxs-lookup"><span data-stu-id="5d7cd-171">Audio Conferencing product names or SKUS used for scripting</span></span>

| <span data-ttu-id="5d7cd-172">Наименование товара</span><span class="sxs-lookup"><span data-stu-id="5d7cd-172">Product name</span></span> | <span data-ttu-id="5d7cd-173">Наименование товарной единицы</span><span class="sxs-lookup"><span data-stu-id="5d7cd-173">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="5d7cd-174">Аудиоконференций (подписка)</span><span class="sxs-lookup"><span data-stu-id="5d7cd-174">Audio Conferencing (subscription)</span></span> | <span data-ttu-id="5d7cd-175">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="5d7cd-175">MCOMEETADV</span></span> | 
| <span data-ttu-id="5d7cd-176">Звукового конференц-связи оплаты за минуту (по мере пользования)</span><span class="sxs-lookup"><span data-stu-id="5d7cd-176">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="5d7cd-177">*Примечание: требуется кредитов коммуникаций для установки и поддержкой*.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-177">*Note: Requires Communications Credits to be set up and enabled*.</span></span> | <span data-ttu-id="5d7cd-178">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="5d7cd-178">MCOMEETACPEA</span></span> |
| <span data-ttu-id="5d7cd-179">Корпоративный E1</span><span class="sxs-lookup"><span data-stu-id="5d7cd-179">Enterprise E1</span></span> | <span data-ttu-id="5d7cd-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="5d7cd-180">STANDARDPACK</span></span> | 
| <span data-ttu-id="5d7cd-181">Корпоративный E3</span><span class="sxs-lookup"><span data-stu-id="5d7cd-181">Enterprise E3</span></span> | <span data-ttu-id="5d7cd-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="5d7cd-182">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="5d7cd-183">Корпоративный E5 (без аудиоконференции)</span><span class="sxs-lookup"><span data-stu-id="5d7cd-183">Enterprise E5 (without Audio Conferencing)</span></span> |  <span data-ttu-id="5d7cd-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="5d7cd-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="5d7cd-185">Корпоративный E5 (с аудиоконференцией)</span><span class="sxs-lookup"><span data-stu-id="5d7cd-185">Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="5d7cd-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="5d7cd-186">ENTERPRISEPREMIUM</span></span> |

##  <a name="communications-credits"></a><span data-ttu-id="5d7cd-187">Кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="5d7cd-187">Communications Credits</span></span>

<span data-ttu-id="5d7cd-188">Вот что нужно знать, прежде чем назначения лицензий кредитов коммуникаций.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-188">Here's what you need to know before assigning Communications Credits licenses.</span></span>

- <span data-ttu-id="5d7cd-189">**E5 корпоративных клиентов**: даже в том случае, если пользователи назначаются E5 корпоративных лицензий, все же рекомендуется назначить их кредитов Communications лицензий.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them Communications Credits licenses.</span></span>

- <span data-ttu-id="5d7cd-190">**Дальнейшие действия**: после назначить эти лицензии, необходимо получить номера телефонов для вашей организации, а затем назначить эти номера для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="5d7cd-191">Пошаговые инструкции см. в статье [Настройка планов звонков](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="5d7cd-191">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="5d7cd-192">Назначение лицензии кредитов коммуникаций для одного пользователя</span><span class="sxs-lookup"><span data-stu-id="5d7cd-192">Assign a Communications Credits license to one user</span></span>

<span data-ttu-id="5d7cd-193">Действия такие же, как назначение лицензии Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="5d7cd-194">Просмотрите [Назначение и удаление лицензий на Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="5d7cd-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="5d7cd-195">Назначение лицензий кредитов коммуникаций в пакетном режиме</span><span class="sxs-lookup"><span data-stu-id="5d7cd-195">Assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="5d7cd-196">Ознакомьтесь с примером сценария для назначения лицензий на аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-196">Take a look at the sample script for assigning Audio Conferencing licenses.</span></span> <span data-ttu-id="5d7cd-197">Обновите сведения для назначения лицензий на кредиты на связь.</span><span class="sxs-lookup"><span data-stu-id="5d7cd-197">Update it with the info for assigning Communications Credits licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5d7cd-198">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="5d7cd-198">Related topics</span></span>

[<span data-ttu-id="5d7cd-199">Настройка планов звонков</span><span class="sxs-lookup"><span data-stu-id="5d7cd-199">Set up Calling Plans</span></span>](set-up-calling-plans.md)
</br>
[<span data-ttu-id="5d7cd-200">Пополнение средств и управление кредитами на связь</span><span class="sxs-lookup"><span data-stu-id="5d7cd-200">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
