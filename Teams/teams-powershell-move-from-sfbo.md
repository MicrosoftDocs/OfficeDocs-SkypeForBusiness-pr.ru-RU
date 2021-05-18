---
title: Переход с Skype для бизнеса Online Connector на модуль Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Узнайте, как перейти Skype для бизнеса Online Connector к Teams PowerShell для управления Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b08505ca97672d5285c8ff46b0e5d3cf58e9f84
ms.sourcegitcommit: 56bebf42f545af57fdf387faa90e555abc8acd40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/18/2021
ms.locfileid: "52513872"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="3abf7-103">Переход с Skype для бизнеса Online Connector на модуль Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="3abf7-103">Migrating from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="3abf7-104">Teams Модуль PowerShell предоставляет полный набор командлетов для управления Teams непосредственно из командной строки PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3abf7-104">Teams PowerShell Module provides a complete set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="3abf7-105">Администраторам не требуется Skype Для бизнеса Online Connector для Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="3abf7-105">Administrators do not require Skype For Business Online Connector for their Teams administration.</span></span>

> [!NOTE]
> <span data-ttu-id="3abf7-106">Teams сообщение центра сообщений (MC244740 от 16 марта 2021 г.); MC250940 от 16 апреля 2021 г.) об этом изменении.</span><span class="sxs-lookup"><span data-stu-id="3abf7-106">Teams administrator were notified through Message center post (MC244740, dated March 16, 2021; MC250940, dated April 16 2021) about this change.</span></span>
>
> <span data-ttu-id="3abf7-107">Teams Модуль PowerShell использует современную проверку подлинности, но для Windows клиента удаленного управления (WinRM) необходимо разрешить базовую проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="3abf7-107">Teams PowerShell Module uses modern authentication, but the underlying Windows Remote Management (WinRM) client must be configured to allow Basic authentication.</span></span> <span data-ttu-id="3abf7-108">Инструкции [о том, как включить проверку](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) подлинности WinRM для Basic, см. в Windows PowerShell и установке приложения.</span><span class="sxs-lookup"><span data-stu-id="3abf7-108">See [Download and install Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) for instructions on how to enable WinRM for Basic authentication.</span></span>

> [!WARNING]
> <span data-ttu-id="3abf7-109">Skype для бизнеса Подключения к сетевым соединителам будут отклоняться с 17 мая 2021 г.</span><span class="sxs-lookup"><span data-stu-id="3abf7-109">Skype for Business Online Connector connections will be rejected starting May 17, 2021.</span></span> <span data-ttu-id="3abf7-110">Обратитесь в службу поддержки Майкрософт за помощью и поддержкой по переходу на Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3abf7-110">Please contact Microsoft Support for help and support for migrating to Teams PowerShell Module.</span></span>

## <a name="how-to-migrate"></a><span data-ttu-id="3abf7-111">Перенос</span><span class="sxs-lookup"><span data-stu-id="3abf7-111">How to Migrate</span></span>

<span data-ttu-id="3abf7-112">Перейти с Skype для бизнеса Online Connector на Teams PowerShell очень просто.</span><span class="sxs-lookup"><span data-stu-id="3abf7-112">Migrating from using Skype for Business Online Connector to Teams PowerShell module is easy and simple.</span></span> <span data-ttu-id="3abf7-113">Ниже объясняется, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="3abf7-113">The below steps explains how to do this.</span></span>

1. <span data-ttu-id="3abf7-114">Установите последнюю версию Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3abf7-114">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="3abf7-115">Дополнительные действия см. [в Microsoft Teams PowerShell.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="3abf7-115">For steps, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

2. <span data-ttu-id="3abf7-116">Удалить соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="3abf7-116">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="3abf7-117">Для этого на панели управления перейдите в программу и функции **,** выберите Skype для бизнеса **Online, Windows PowerShell module**, а затем **выберите** Удалить .</span><span class="sxs-lookup"><span data-stu-id="3abf7-117">To do this, in Control Panel, go to **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span>

3. <span data-ttu-id="3abf7-118">В сценариях PowerShell измените имя модуля, на который ссылается ```Import-Module```</span><span class="sxs-lookup"><span data-stu-id="3abf7-118">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from</span></span>

    <span data-ttu-id="3abf7-119">`SkypeOnlineConnector` или `LyncOnlineConnector` в `MicrosoftTeams` .</span><span class="sxs-lookup"><span data-stu-id="3abf7-119">`SkypeOnlineConnector` or `LyncOnlineConnector` to `MicrosoftTeams`.</span></span>

    <span data-ttu-id="3abf7-120">Например, измените `Import-Module -Name SkypeOnlineConnector` на `Import-Module -Name MicrosoftTeams` .</span><span class="sxs-lookup"><span data-stu-id="3abf7-120">For example, change `Import-Module -Name SkypeOnlineConnector` to `Import-Module -Name MicrosoftTeams`.</span></span>

4. <span data-ttu-id="3abf7-121">При использовании Teams PowerShell Module 2.0 или более поздней версии обновите сценарии, которые ссылаются на `New-CsOnlineSession` `Connect-MicrosoftTeams` .</span><span class="sxs-lookup"><span data-stu-id="3abf7-121">When using Teams PowerShell Module 2.0 or later, update your scripts that refers `New-CsOnlineSession` to `Connect-MicrosoftTeams`.</span></span> <span data-ttu-id="3abf7-122">`Import-PsSession`больше не требуется создавать сеанс удаленной Skype для бизнеса PowerShell в Интернете, так как он делается неявным при использовании `Connect-MicrosoftTeams` .</span><span class="sxs-lookup"><span data-stu-id="3abf7-122">`Import-PsSession` is no longer required to establish a Skype for Business Online Remote PowerShell Session as that is done implicit when using `Connect-MicrosoftTeams`.</span></span>

    ```powershell
       # When using the Skype for Business online connector
         
         # Establishing a session
         Import-Module SkypeOnlineConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session 
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # When using Teams PowerShell Module 2.0 or later
       
         # Establishing a session
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session  
         Disconnect-MicrosoftTeams
    ```

## <a name="online-support"></a><span data-ttu-id="3abf7-123">Поддержка в Интернете</span><span class="sxs-lookup"><span data-stu-id="3abf7-123">Online Support</span></span>

<span data-ttu-id="3abf7-124">Экономите время, отправив запрос на обслуживание через Интернет.</span><span class="sxs-lookup"><span data-stu-id="3abf7-124">Save time by starting your service request online.</span></span> <span data-ttu-id="3abf7-125">Мы поможем вам найти решение или подключиться к службе технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="3abf7-125">We'll help you find a solution or connect you to technical support.</span></span>

1.  <span data-ttu-id="3abf7-126">Перейдите в Центр администрирования по запросу [https://admin.microsoft.com](https://admin.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="3abf7-126">Go to the admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span> <span data-ttu-id="3abf7-127">Если вы получаете сообщение о том, что у вас нет разрешения на доступ к этой странице или выполнение этого действия, вы не администратор. У Кто есть разрешения администратора в моей компании?</span><span class="sxs-lookup"><span data-stu-id="3abf7-127">If you get a message that says you don't have permission to access this page or perform this action, then you aren't an admin. Who has admin permissions in my business?</span></span>

2.  <span data-ttu-id="3abf7-128">Выберите нужна **помощь?** Кнопку.</span><span class="sxs-lookup"><span data-stu-id="3abf7-128">Select the **Need help**? button.</span></span>

3.  <span data-ttu-id="3abf7-129">В области **Нужна помощь?** расскажите нам, с чем вам нужна помощь, и нажмите ввод.</span><span class="sxs-lookup"><span data-stu-id="3abf7-129">In the **Need help**? pane, tell us what you need help with, and then press Enter.</span></span>

4.  <span data-ttu-id="3abf7-130">Если результаты не помогли, выберите Обратиться **в службу поддержки**.</span><span class="sxs-lookup"><span data-stu-id="3abf7-130">If the results don't help, select **Contact support**.</span></span>

5.  <span data-ttu-id="3abf7-131">Введите описание проблемы, подтвердите свой номер контакта и адрес электронной почты, выберите предпочтительный способ связи, а затем выберите Связаться **со мной**.</span><span class="sxs-lookup"><span data-stu-id="3abf7-131">Enter a description of your issue, confirm your contact number and email address, select your preferred contact method, and then select **Contact me**.</span></span> <span data-ttu-id="3abf7-132">Ожидаемое время ожидания указано в области Нужна помощь? Панели.</span><span class="sxs-lookup"><span data-stu-id="3abf7-132">The expected wait time is indicated in the Need help? pane.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3abf7-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3abf7-133">Related topics</span></span>

[<span data-ttu-id="3abf7-134">Установка Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="3abf7-134">Install Microsoft Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="3abf7-135">Управление Teams с помощью Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="3abf7-135">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="3abf7-136">Teams Заметки о выпуске PowerShell</span><span class="sxs-lookup"><span data-stu-id="3abf7-136">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="3abf7-137">Microsoft Teams ссылки на cmdlet</span><span class="sxs-lookup"><span data-stu-id="3abf7-137">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="3abf7-138">Skype для бизнеса ссылки на cmdlet</span><span class="sxs-lookup"><span data-stu-id="3abf7-138">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
