---
title: Включение и отключение гостевого доступа для Microsoft Teams
author: LaithAlShamri
ms.author: lolaj
manager: serdars
ms.date: 10/11/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Включение и отключение гостевого доступа в Microsoft Teams
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ab67b3fa9ad58c1aa3e8fdd254e3b3515743b4c
ms.sourcegitcommit: 9dd5d8fe6888f0c7d2df1e40fdd8b4c80512f8f9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "25498123"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="290a6-103">Включение и отключение гостевого доступа для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="290a6-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="290a6-104">Являясь администратором Office 365, вы должны включить функцию гостевого доступа, прежде чем вы или пользователи вашей организации (в частности, владельцы команд) смогут добавлять гостей.</span><span class="sxs-lookup"><span data-stu-id="290a6-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="290a6-105">Параметры гостей задаются в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="290a6-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="290a6-106">Чтобы эти изменения вступили в силу в рамках всей организации Office 365, требуется от 2 до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="290a6-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="290a6-107">Если пользователь получает сообщение "Обратитесь к администратору" при попытке добавить гостя в команду, вероятнее всего, что гостевой доступ еще не включен либо соответствующие параметры еще не вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="290a6-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="290a6-108">Чтобы полностью включить все возможности гостевого доступа, важно понять основную зависимость между Microsoft Teams, Azure Active Directory и Office 365.</span><span class="sxs-lookup"><span data-stu-id="290a6-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="290a6-109">Дополнительные сведения см. в статье [Авторизация гостевого доступа в Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="290a6-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a><span data-ttu-id="290a6-110">Настройка доступа к гостевой в группы & Скайп по центру администрирования бизнеса</span><span class="sxs-lookup"><span data-stu-id="290a6-110">Configure guest access in the Teams & Skype for Business admin center</span></span>

1.  <span data-ttu-id="290a6-111">Войдите в группы & Скайп по центру администрирования бизнеса.</span><span class="sxs-lookup"><span data-stu-id="290a6-111">Sign in to the Teams & Skype for Business admin center.</span></span>

2.  <span data-ttu-id="290a6-112">Выберите пункт **Параметры масштабе организации** > **доступ в качестве гостя**.</span><span class="sxs-lookup"><span data-stu-id="290a6-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="290a6-113">Значение переключатель **Разрешить доступ гостя в группах Microsoft** **на**.</span><span class="sxs-lookup"><span data-stu-id="290a6-113">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="290a6-114">Разрешить переключатель доступа гостя значение на</span><span class="sxs-lookup"><span data-stu-id="290a6-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="290a6-115">Задайте переключение для **вызова**, **собрания**и **системы обмена сообщениями** для **включено** или **отключено**, в зависимости от доступа, которые необходимо разрешить.</span><span class="sxs-lookup"><span data-stu-id="290a6-115">Set the toggles for **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the access you want to allow.</span></span>

5.  <span data-ttu-id="290a6-116">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="290a6-116">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="290a6-117">Чтобы включить доступ в качестве гостя или отключить с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="290a6-117">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="290a6-118">Загрузить Скайп для модуля Business Online PowerShell изhttps://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="290a6-118">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="290a6-119">Подключите сеанс PowerShell Скайп для бизнеса в Интернет конечной точки.</span><span class="sxs-lookup"><span data-stu-id="290a6-119">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="290a6-120">Проверьте конфигурацию и, если `AllowGuestUser` — это `$False`, используйте командлет [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) Установка для `$True`.</span><span class="sxs-lookup"><span data-stu-id="290a6-120">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    AllowTBotProactiveMessaging      : False
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="290a6-121">Теперь можно создать гостевых пользователей в группах для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="290a6-121">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="290a6-122">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="290a6-122">More information</span></span>

<span data-ttu-id="290a6-123">В следующем видео для получения дополнительных сведений о доступ в качестве гостя.</span><span class="sxs-lookup"><span data-stu-id="290a6-123">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="290a6-124">Добавление гостей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="290a6-124">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
