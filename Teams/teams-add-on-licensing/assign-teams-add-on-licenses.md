---
title: Назначение пользователям лицензий на надстройки Teams
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
description: Узнайте, как назначать пользователям лицензии на надстройки Teams для таких функций, как аудиоконференция, телефонная система и планы звонков.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dd09ae11104aa0297a12417d4c267edfc17cf3f
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788743"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="4788d-103">Назначение пользователям лицензий на надстройки Teams</span><span class="sxs-lookup"><span data-stu-id="4788d-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="4788d-104">Лицензии на надстройки — это лицензии на определенные функции Teams, такие как аудиоконференция, телефонная система и планы звонков.</span><span class="sxs-lookup"><span data-stu-id="4788d-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="4788d-105">В этой статье описано, как массово назначить лицензии на надстройки отдельным пользователям и большим наборам пользователей.</span><span class="sxs-lookup"><span data-stu-id="4788d-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="4788d-106">См. [лицензирование надстройки](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) Teams для функций Teams, доступных с лицензиями на надстройки.</span><span class="sxs-lookup"><span data-stu-id="4788d-106">See [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="4788d-107">Здесь также представлены сведения о том, какие лицензии необходимо приобрести и как их приобрести (в зависимости от плана), чтобы пользователи могли получить доступ к таким функциям, как аудиоконференция, бесплатные номера и возможность звонить на телефонные номера за пределы организации.</span><span class="sxs-lookup"><span data-stu-id="4788d-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="4788d-108">После того как вы решите, какие функции нужны пользователям, назначьте им лицензии.</span><span class="sxs-lookup"><span data-stu-id="4788d-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="4788d-109">Для назначения лицензий пользователям в организации можно использовать Центр администрирования Microsoft 365 или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4788d-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="4788d-110">Для управления лицензиями необходимо быть глобальным администратором или администратором управления пользователями.</span><span class="sxs-lookup"><span data-stu-id="4788d-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="4788d-111">Что нужно знать перед назначением лицензий на телефонную систему, план звонков и кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="4788d-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="4788d-112">Прежде чем начать, просмотрите следующие вопросы:</span><span class="sxs-lookup"><span data-stu-id="4788d-112">Before you get started, review the following:</span></span>

- <span data-ttu-id="4788d-113">Если вы используете для гибридных пользователей возможность подключения к локальной телефонной сети общего перейти на ЗВОНКОВ, необходимо только назначить лицензию на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="4788d-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="4788d-114">Не назначать лицензию на план звонков.</span><span class="sxs-lookup"><span data-stu-id="4788d-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="4788d-115">Из-за задержки между Microsoft 365 и Microsoft Teams назначение пользователю плана звонков после назначения лицензии может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="4788d-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="4788d-116">Если пользователю не назначен план звонков по и после 24 часов, обратитесь в службу поддержки по продуктам для [бизнеса— справка для администраторов.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="4788d-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="4788d-117">Если приобретено неправильное количество лицензий, вы получите сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="4788d-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="4788d-118">Если вам нужно приобрести дополнительные лицензии на план звонков, выберите этот вариант.</span><span class="sxs-lookup"><span data-stu-id="4788d-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="4788d-119">Даже если вашим пользователям назначены лицензии на корпоративный [](../what-are-communications-credits.md) E5, им необходимо назначить лицензии на кредиты на связь, если они захотят звонить или принимать звонки через ПС.</span><span class="sxs-lookup"><span data-stu-id="4788d-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="4788d-120">После назначения пользователям лицензий на план звонков или кредиты на связь вам потребуется получить номера телефонов для организации, а затем назначить их пользователям.</span><span class="sxs-lookup"><span data-stu-id="4788d-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="4788d-121">Пошаговые инструкции см. в статье [Настройка планов звонков](../set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="4788d-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="4788d-122">Использование Центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4788d-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="4788d-123">Для назначения лицензий отдельным пользователям или небольшим наборам пользователей за раз используйте Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4788d-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="4788d-124">Лицензии можно назначать на странице **"Лицензии"** (не более 20 пользователей одновременно) или на странице **"Активные** пользователи".</span><span class="sxs-lookup"><span data-stu-id="4788d-124">You can assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="4788d-125">Выбор метода зависит от того, хотите ли вы управлять лицензиями на продукты для определенных пользователей или лицензиями пользователей для определенных продуктов.</span><span class="sxs-lookup"><span data-stu-id="4788d-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="4788d-126">Пошаговую инструкцию см. в инструкции по [назначению лицензий пользователям.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="4788d-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="4788d-127">Если необходимо назначить лицензии большому количеству пользователей, например сотням или тысячам пользователей, используйте Powershell или групповое лицензирование в [Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="4788d-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="4788d-128">С помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4788d-128">Using PowerShell</span></span>

<span data-ttu-id="4788d-129">Используйте PowerShell для массового назначения лицензий пользователям.</span><span class="sxs-lookup"><span data-stu-id="4788d-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="4788d-130">Дополнительные данные см. в записях [PowerShell для назначения лицензий учетным записям пользователей.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="4788d-130">To learn more, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="4788d-131">Пример сценария</span><span class="sxs-lookup"><span data-stu-id="4788d-131">Example script</span></span>

<span data-ttu-id="4788d-132">Вот пример использования сценария для назначения лицензий пользователям.</span><span class="sxs-lookup"><span data-stu-id="4788d-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="4788d-133">Установите 64-битную версию Microsoft Online Services [для ИТ-специалистов, RTW.](https://go.microsoft.com/fwlink/p/?LinkId=286152)</span><span class="sxs-lookup"><span data-stu-id="4788d-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
2. <span data-ttu-id="4788d-134">Установите модуль Microsoft Azure Active Directory для Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4788d-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="4788d-135">Откройте командную Windows PowerShell с повышенными Windows PowerShell (запустите Windows PowerShell от имени администратора).</span><span class="sxs-lookup"><span data-stu-id="4788d-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="4788d-136">Выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="4788d-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="4788d-137">Если вам будет предложено установить поставщика NuGet, введите **Y** и нажмите ввод.</span><span class="sxs-lookup"><span data-stu-id="4788d-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="4788d-138">Если вам будет предложено установить модуль из PSGallery, введите **Y** и нажмите ввод.</span><span class="sxs-lookup"><span data-stu-id="4788d-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="4788d-139">В командной Windows PowerShell запустите следующий сценарий, чтобы назначить лицензии пользователям, где находится название организации и идентификатор лицензии, которую вы \<CompanyName:License> хотите назначить.</span><span class="sxs-lookup"><span data-stu-id="4788d-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="4788d-140">Например, litwareinc:MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="4788d-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="4788d-141">Идентификатор отличается от удобного имени лицензии.</span><span class="sxs-lookup"><span data-stu-id="4788d-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="4788d-142">Например, идентификатором для аудиоконференции будет MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="4788d-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="4788d-143">Подробнее см. в названиях продуктов и [идентификаторах SKU для лицензирования.](#product-names-and-sku-identifiers-for-licensing)</span><span class="sxs-lookup"><span data-stu-id="4788d-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

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

    <span data-ttu-id="4788d-144">Например, чтобы назначить лицензии на Microsoft 365 корпоративный 1 и аудиоконференцию, используйте в сценарии следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="4788d-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="4788d-145">Чтобы назначить лицензию на Microsoft Business Voice (без плана звонков), используйте в сценарии следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="4788d-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="4788d-146">Названия продуктов и идентификаторы SKU для лицензирования</span><span class="sxs-lookup"><span data-stu-id="4788d-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="4788d-147">Вот неполный список названий продуктов и соответствующих названий их составных номеров SKU, которые можно использовать в качестве справки при использовании PowerShell для управления лицензиями в Teams.</span><span class="sxs-lookup"><span data-stu-id="4788d-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="4788d-148">Дополнительные данные см. в справке по лицензиям и службам [PowerShell,](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)именам продуктов и планам обслуживания для лицензирования [и](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)справке по SKU для [образования.](../sku-reference-edu.md)</span><span class="sxs-lookup"><span data-stu-id="4788d-148">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="4788d-149">Наименование товара</span><span class="sxs-lookup"><span data-stu-id="4788d-149">Product name</span></span>| <span data-ttu-id="4788d-150">Наименование товарной единицы</span><span class="sxs-lookup"><span data-stu-id="4788d-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="4788d-151">Microsoft Enterprise E5 (с телефонной системой)</span><span class="sxs-lookup"><span data-stu-id="4788d-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="4788d-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="4788d-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="4788d-153">Microsoft Enterprise E5 (без аудиоконференции)</span><span class="sxs-lookup"><span data-stu-id="4788d-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="4788d-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="4788d-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="4788d-155">Microsoft Enterprise E5 (с аудиоконференцией)</span><span class="sxs-lookup"><span data-stu-id="4788d-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="4788d-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="4788d-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="4788d-157">Microsoft Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="4788d-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="4788d-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="4788d-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="4788d-159">Microsoft Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="4788d-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="4788d-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="4788d-160">STANDARDPACK</span></span> |
| <span data-ttu-id="4788d-161">Microsoft 365 бизнес базовый</span><span class="sxs-lookup"><span data-stu-id="4788d-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="4788d-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="4788d-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="4788d-163">Microsoft 365 бизнес стандарт</span><span class="sxs-lookup"><span data-stu-id="4788d-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="4788d-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="4788d-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="4788d-165">Microsoft 365 бизнес</span><span class="sxs-lookup"><span data-stu-id="4788d-165">Microsoft 365 Business</span></span> | <span data-ttu-id="4788d-166">SPB</span><span class="sxs-lookup"><span data-stu-id="4788d-166">SPB</span></span>|
| <span data-ttu-id="4788d-167">Microsoft Business Voice (Канада)</span><span class="sxs-lookup"><span data-stu-id="4788d-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="4788d-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="4788d-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="4788d-169">Microsoft Business Voice (Соединенное Королевство)</span><span class="sxs-lookup"><span data-stu-id="4788d-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="4788d-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="4788d-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="4788d-171">Microsoft Business Voice (США)</span><span class="sxs-lookup"><span data-stu-id="4788d-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="4788d-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="4788d-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="4788d-173">Microsoft Business Voice (без плана звонков)</span><span class="sxs-lookup"><span data-stu-id="4788d-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="4788d-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="4788d-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="4788d-175">Microsoft Business Voice (без плана звонков) для США</span><span class="sxs-lookup"><span data-stu-id="4788d-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="4788d-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="4788d-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="4788d-177">Аудиоконференция</span><span class="sxs-lookup"><span data-stu-id="4788d-177">Audio Conferencing</span></span> | <span data-ttu-id="4788d-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="4788d-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="4788d-179">Аудиоконференция с поминутной оплатой (оплата по мере ее оплаты)</span><span class="sxs-lookup"><span data-stu-id="4788d-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="4788d-180">*Требуется настроить и включить кредиты на связь.*</span><span class="sxs-lookup"><span data-stu-id="4788d-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="4788d-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="4788d-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="4788d-182">Телефонная система</span><span class="sxs-lookup"><span data-stu-id="4788d-182">Phone System</span></span> | <span data-ttu-id="4788d-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="4788d-183">MCOEV</span></span> |
| <span data-ttu-id="4788d-184">План внутренних и международных звонков</span><span class="sxs-lookup"><span data-stu-id="4788d-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="4788d-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="4788d-185">MCOPSTN2</span></span> |
| <span data-ttu-id="4788d-186">План внутренних звонков (3000 минут на пользователя в месяц для США/PR/CA, 1200 минут на пользователя в месяц для стран ЕС)</span><span class="sxs-lookup"><span data-stu-id="4788d-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="4788d-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="4788d-187">MCOPSTN1</span></span> |
| <span data-ttu-id="4788d-188">План внутренних звонков (120 минут на каждого пользователя в месяц для каждой страны)</span><span class="sxs-lookup"><span data-stu-id="4788d-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="4788d-189">*Этот план не доступен в США.*</span><span class="sxs-lookup"><span data-stu-id="4788d-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="4788d-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="4788d-190">MCOPSTN5</span></span> |
| <span data-ttu-id="4788d-191">План внутренних звонков (240 минут на пользователя в месяц для каждой страны)</span><span class="sxs-lookup"><span data-stu-id="4788d-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="4788d-192">*Этот план не доступен в США.*</span><span class="sxs-lookup"><span data-stu-id="4788d-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="4788d-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="4788d-193">MCOPSTN6</span></span> |
| <span data-ttu-id="4788d-194">Кредиты на связь</span><span class="sxs-lookup"><span data-stu-id="4788d-194">Communications Credits</span></span> | <span data-ttu-id="4788d-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="4788d-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="4788d-196">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="4788d-196">Related topics</span></span>

- [<span data-ttu-id="4788d-197">Лицензирование надстроек Teams</span><span class="sxs-lookup"><span data-stu-id="4788d-197">Teams add-on licensing</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [<span data-ttu-id="4788d-198">Управление доступом пользователей к Teams</span><span class="sxs-lookup"><span data-stu-id="4788d-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="4788d-199">Просмотр лицензий и служб с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4788d-199">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="4788d-200">Названия продуктов и идентификаторы планов служб для лицензирования</span><span class="sxs-lookup"><span data-stu-id="4788d-200">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="4788d-201">Справка по SKU для образования</span><span class="sxs-lookup"><span data-stu-id="4788d-201">Education SKU reference</span></span>](../sku-reference-edu.md)