---
title: Назначение лицензий на надстройки Teams пользователям
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Сведения о назначении пользователям лицензий на надстройки Teams, таких как голосовые конференции, телефонная система и планы звонков.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dd09ae11104aa0297a12417d4c267edfc17cf3f
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788743"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="9909f-103">Назначение лицензий на надстройки Teams пользователям</span><span class="sxs-lookup"><span data-stu-id="9909f-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="9909f-104">Лицензии на надстройки — это лицензии для конкретных функций групп, таких как голосовая конференция, телефонная система и планы звонков.</span><span class="sxs-lookup"><span data-stu-id="9909f-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="9909f-105">В этой статье описано, как назначать лицензии для отдельных пользователей и больших наборов пользователей.</span><span class="sxs-lookup"><span data-stu-id="9909f-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="9909f-106">Ознакомьтесь с возможностями [лицензирования надстроек Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) для Teams, которые доступны при использовании лицензий на надстройки.</span><span class="sxs-lookup"><span data-stu-id="9909f-106">See [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="9909f-107">Вы также найдете сведения о лицензиях, которые нужно приобрести, и о том, как их приобрести (в зависимости от вашего плана), чтобы пользователи могли получать такие функции, как голосовые конференции, бесплатные номера и возможность звонить на телефонные номера за пределами вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9909f-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="9909f-108">После того как вы решите, какие функции вы хотите использовать для ваших пользователей, назначьте им лицензии.</span><span class="sxs-lookup"><span data-stu-id="9909f-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="9909f-109">Вы можете назначать лицензии пользователям в Организации с помощью центра администрирования Microsoft 365 или оболочки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9909f-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="9909f-110">Для управления лицензиями необходимо быть глобальным администратором или администратором управления пользователями.</span><span class="sxs-lookup"><span data-stu-id="9909f-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="9909f-111">Что нужно знать перед назначением лицензий на телефонную систему, план звонков и кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="9909f-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="9909f-112">Прежде чем приступить к работе, ознакомьтесь со следующими статьями:</span><span class="sxs-lookup"><span data-stu-id="9909f-112">Before you get started, review the following:</span></span>

- <span data-ttu-id="9909f-113">Если вы используете локальную телефонную сеть общего коммутируемого подключения (PSTN) для гибридных пользователей, вам нужно назначить лицензию на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="9909f-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="9909f-114">Не назначайте лицензию на план звонков.</span><span class="sxs-lookup"><span data-stu-id="9909f-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="9909f-115">Из-за задержки между Microsoft 365 и Microsoft Teams пользователю может потребоваться до 24 часов, после того как пользователь сможет назначить план звонков после того, как вы настроили лицензию.</span><span class="sxs-lookup"><span data-stu-id="9909f-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="9909f-116">Если пользователь не назначил план звонков через 24 часа, обратитесь в [службу поддержки для бизнес-продуктов — Справка для администраторов](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="9909f-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="9909f-117">Если вы не приобрели правильное количество лицензий, вы получите сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="9909f-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="9909f-118">Если вам нужно приобрести дополнительные лицензии на план звонков, выберите вариант "Купить".</span><span class="sxs-lookup"><span data-stu-id="9909f-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="9909f-119">Даже если пользователям назначены лицензии на "Корпоративное" + +, вам по-прежнему [необходимо назначать лицензии](../what-are-communications-credits.md) на получение абонентов, если они хотят совершать и принимать звонки от КТСОП.</span><span class="sxs-lookup"><span data-stu-id="9909f-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="9909f-120">После назначения пользователям лицензий на тарифные планы или кредиты на связь с пользователями необходимо получить номера телефонов для своей организации, а затем назначить их пользователям.</span><span class="sxs-lookup"><span data-stu-id="9909f-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="9909f-121">Пошаговые инструкции см. в статье [Настройка планов звонков](../set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="9909f-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="9909f-122">Использование центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9909f-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="9909f-123">С помощью центра администрирования Microsoft 365 вы можете назначать лицензии отдельным пользователям или небольшим наборам пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="9909f-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="9909f-124">Вы можете назначать лицензии на странице **лицензий** (до 20 пользователей одновременно) или на странице " **Активные пользователи** ".</span><span class="sxs-lookup"><span data-stu-id="9909f-124">You can assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="9909f-125">Выбор метода зависит от того, хотите ли вы управлять лицензиями на продукты для конкретных пользователей или управлять лицензиями пользователей для конкретных продуктов.</span><span class="sxs-lookup"><span data-stu-id="9909f-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="9909f-126">Пошаговые инструкции приведены [в статье Назначение лицензий пользователям](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="9909f-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="9909f-127">Если необходимо назначить лицензии для большого числа пользователей, например сотни или тысячи пользователей, используйте PowerShell или [Лицензирование на основе групп в Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="9909f-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="9909f-128">Использование PowerShell</span><span class="sxs-lookup"><span data-stu-id="9909f-128">Using PowerShell</span></span>

<span data-ttu-id="9909f-129">С помощью PowerShell можно назначать пользователям лицензии для массовых операций.</span><span class="sxs-lookup"><span data-stu-id="9909f-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="9909f-130">Дополнительные сведения можно найти в статье [Назначение лицензий для учетных записей пользователей с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="9909f-130">To learn more, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="9909f-131">Пример сценария</span><span class="sxs-lookup"><span data-stu-id="9909f-131">Example script</span></span>

<span data-ttu-id="9909f-132">Ниже приведен пример использования сценария для назначения лицензий пользователям.</span><span class="sxs-lookup"><span data-stu-id="9909f-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="9909f-133">Установите 64-разрядную версию [помощника по входу в Microsoft Online Services для ИТ-специалистов RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span><span class="sxs-lookup"><span data-stu-id="9909f-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
2. <span data-ttu-id="9909f-134">Установите модуль Microsoft Azure Active Directory для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9909f-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="9909f-135">Откройте командную команду Windows PowerShell с повышенными привилегиями (запустите Windows PowerShell от имени администратора).</span><span class="sxs-lookup"><span data-stu-id="9909f-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="9909f-136">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="9909f-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="9909f-137">Если вам будет предложено установить поставщик NuGet, введите **Y**и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="9909f-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="9909f-138">Если вам будет предложено установить модуль из PSGallery, введите **Y**и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="9909f-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="9909f-139">В командной строке Windows PowerShell выполните следующий сценарий для назначения лицензий пользователям, где указаны \<CompanyName:License> название организации и идентификатор для лицензии, которую вы хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="9909f-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="9909f-140">Например, плана litwareinc: MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="9909f-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="9909f-141">Идентификатор отличается от понятного имени лицензии.</span><span class="sxs-lookup"><span data-stu-id="9909f-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="9909f-142">Например, идентификатором для голосовой конференции является MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="9909f-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="9909f-143">Дополнительные сведения можно найти в разделе [наименования продуктов и идентификаторы SKU для лицензирования](#product-names-and-sku-identifiers-for-licensing).</span><span class="sxs-lookup"><span data-stu-id="9909f-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
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
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    <span data-ttu-id="9909f-144">Например, для назначения лицензий Microsoft 365 Enterprise 1 и голосовой связи в сценарии используется следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9909f-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="9909f-145">Чтобы назначить лицензию Microsoft Business Voice (без плана звонков), используйте в сценарии следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9909f-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="9909f-146">Названия продуктов и идентификаторы SKU для лицензирования</span><span class="sxs-lookup"><span data-stu-id="9909f-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="9909f-147">Ниже приводится частичный список названий продуктов и соответствующих им названий частей SKU, которые можно использовать в качестве справочных данных при использовании PowerShell для управления лицензиями в Teams.</span><span class="sxs-lookup"><span data-stu-id="9909f-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="9909f-148">Дополнительные сведения можно найти в статье [Просмотр лицензий и служб с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [названий продуктов и идентификаторов планов обслуживания для лицензирования](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)и [справочника по образованиям на образовательных SKU](../sku-reference-edu.md).</span><span class="sxs-lookup"><span data-stu-id="9909f-148">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="9909f-149">Наименование товара</span><span class="sxs-lookup"><span data-stu-id="9909f-149">Product name</span></span>| <span data-ttu-id="9909f-150">Наименование товарной единицы</span><span class="sxs-lookup"><span data-stu-id="9909f-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="9909f-151">Microsoft Enterprise ~ (с телефонной системой)</span><span class="sxs-lookup"><span data-stu-id="9909f-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="9909f-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="9909f-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="9909f-153">Microsoft корпоративный + ~ (без голосовой конференции)</span><span class="sxs-lookup"><span data-stu-id="9909f-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="9909f-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="9909f-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="9909f-155">Microsoft Корпоративный текст для корпоративных клиентов (с голосовой Конференцией)</span><span class="sxs-lookup"><span data-stu-id="9909f-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="9909f-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="9909f-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="9909f-157">Microsoft корпоративный E3</span><span class="sxs-lookup"><span data-stu-id="9909f-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="9909f-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="9909f-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="9909f-159">Microsoft корпоративный E1</span><span class="sxs-lookup"><span data-stu-id="9909f-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="9909f-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="9909f-160">STANDARDPACK</span></span> |
| <span data-ttu-id="9909f-161">Microsoft 365 бизнес базовый</span><span class="sxs-lookup"><span data-stu-id="9909f-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="9909f-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="9909f-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="9909f-163">Microsoft 365 бизнес стандарт</span><span class="sxs-lookup"><span data-stu-id="9909f-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="9909f-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="9909f-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="9909f-165">Microsoft 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="9909f-165">Microsoft 365 Business</span></span> | <span data-ttu-id="9909f-166">SPB</span><span class="sxs-lookup"><span data-stu-id="9909f-166">SPB</span></span>|
| <span data-ttu-id="9909f-167">Microsoft Business Voice (Канада)</span><span class="sxs-lookup"><span data-stu-id="9909f-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="9909f-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="9909f-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="9909f-169">Microsoft Business Voice (Соединенное Королевство)</span><span class="sxs-lookup"><span data-stu-id="9909f-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="9909f-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="9909f-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="9909f-171">Microsoft Business Voice (США)</span><span class="sxs-lookup"><span data-stu-id="9909f-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="9909f-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="9909f-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="9909f-173">Microsoft Business Voice (без тарифного плана)</span><span class="sxs-lookup"><span data-stu-id="9909f-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="9909f-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="9909f-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="9909f-175">Microsoft Business Voice (без тарифного плана) для Соединенных Штатов Америки</span><span class="sxs-lookup"><span data-stu-id="9909f-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="9909f-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="9909f-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="9909f-177">Аудиоконференция</span><span class="sxs-lookup"><span data-stu-id="9909f-177">Audio Conferencing</span></span> | <span data-ttu-id="9909f-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="9909f-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="9909f-179">Оплата для голосовой конференции за минуту (оплата за один звонок)</span><span class="sxs-lookup"><span data-stu-id="9909f-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="9909f-180">*Требует настройки и включения кредитов на связь.*</span><span class="sxs-lookup"><span data-stu-id="9909f-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="9909f-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="9909f-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="9909f-182">Телефонная система</span><span class="sxs-lookup"><span data-stu-id="9909f-182">Phone System</span></span> | <span data-ttu-id="9909f-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="9909f-183">MCOEV</span></span> |
| <span data-ttu-id="9909f-184">План внутренних и международных звонков</span><span class="sxs-lookup"><span data-stu-id="9909f-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="9909f-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="9909f-185">MCOPSTN2</span></span> |
| <span data-ttu-id="9909f-186">План внутренних вызовов (3000 минут на пользователя/месяц для US/PR/CA, 1200 минут на пользователя/месяц для стран ЕС)</span><span class="sxs-lookup"><span data-stu-id="9909f-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="9909f-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="9909f-187">MCOPSTN1</span></span> |
| <span data-ttu-id="9909f-188">План внутренних вызовов (120 минут на пользователя/месяц для каждой страны)</span><span class="sxs-lookup"><span data-stu-id="9909f-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="9909f-189">*Этот план недоступен в Соединенных Штатах.*</span><span class="sxs-lookup"><span data-stu-id="9909f-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="9909f-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="9909f-190">MCOPSTN5</span></span> |
| <span data-ttu-id="9909f-191">План внутренних вызовов (240 минут на пользователя/месяц для каждой страны)</span><span class="sxs-lookup"><span data-stu-id="9909f-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="9909f-192">*Этот план недоступен в Соединенных Штатах.*</span><span class="sxs-lookup"><span data-stu-id="9909f-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="9909f-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="9909f-193">MCOPSTN6</span></span> |
| <span data-ttu-id="9909f-194">Кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="9909f-194">Communications Credits</span></span> | <span data-ttu-id="9909f-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="9909f-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9909f-196">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="9909f-196">Related topics</span></span>

- [<span data-ttu-id="9909f-197">Лицензирование надстроек Teams</span><span class="sxs-lookup"><span data-stu-id="9909f-197">Teams add-on licensing</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [<span data-ttu-id="9909f-198">Управление доступом пользователей к Teams</span><span class="sxs-lookup"><span data-stu-id="9909f-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="9909f-199">Просмотр лицензий и служб с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="9909f-199">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="9909f-200">Названия продуктов и идентификаторы планов служб для лицензирования</span><span class="sxs-lookup"><span data-stu-id="9909f-200">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="9909f-201">Справочник по образовательной конфигурации</span><span class="sxs-lookup"><span data-stu-id="9909f-201">Education SKU reference</span></span>](../sku-reference-edu.md)