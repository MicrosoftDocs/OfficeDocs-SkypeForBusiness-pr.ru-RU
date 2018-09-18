---
title: Установка Microsoft Teams с помощью MSI
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: Администраторы могут использовать MSI Teams для массового развертывания Microsoft Teams для отдельных пользователей или на отдельных компьютерах.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78ceb6fa0cd70b5cf6fc25bc9537939beea99b7c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882040"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="7a394-103">Установка Microsoft Teams с помощью MSI</span><span class="sxs-lookup"><span data-stu-id="7a394-103">Install Microsoft Teams using MSI</span></span>
=================================

<span data-ttu-id="7a394-104">Чтобы использовать System Center Configuration Manager, групповую политику или любые сторонние механизмы распространения для обширного развертывания, корпорация Майкрософт предоставила файлы MSI (как [32-](https://aka.ms/teams32bitmsi), так и [64-разрядные](https://aka.ms/teams64bitmsi)), которые администраторы могут использовать для массового развертывания Teams для отдельных пользователей или на отдельных компьютерах.</span><span class="sxs-lookup"><span data-stu-id="7a394-104">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="7a394-105">Администраторы могут использовать эти файлы для удаленного развертывания Teams, чтобы пользователям не нужно было вручную скачивать приложение Teams.</span><span class="sxs-lookup"><span data-stu-id="7a394-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="7a394-106">После развертывания Teams автоматически запускается для всех пользователей, выполнивших вход на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="7a394-106">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="7a394-107">Мы рекомендуем развертывать пакет на компьютере, чтобы все новые пользователи этого компьютера также могли воспользоваться преимуществами данного развертывания.</span><span class="sxs-lookup"><span data-stu-id="7a394-107">We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="7a394-108">Дополнительные сведения о SCCM см. в статье [Знакомство с System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="7a394-108">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="7a394-109">Процедура развертывания (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="7a394-109">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="7a394-110">Получите последний пакет.</span><span class="sxs-lookup"><span data-stu-id="7a394-110">Retrieve the latest package.</span></span>
2. <span data-ttu-id="7a394-111">Используйте настройки по умолчанию, заданные MSI.</span><span class="sxs-lookup"><span data-stu-id="7a394-111">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="7a394-112">По возможности разверните на компьютерах.</span><span class="sxs-lookup"><span data-stu-id="7a394-112">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="7a394-113">Принцип работы пакета MSI Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7a394-113">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="7a394-114">MSI Teams помещает установщик в папку Program Files.</span><span class="sxs-lookup"><span data-stu-id="7a394-114">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="7a394-115">Когда пользователь входит в новый профиль пользователя Windows, запускается установщик и в папку appdata этого пользователя устанавливается копия приложения Teams.</span><span class="sxs-lookup"><span data-stu-id="7a394-115">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="7a394-116">Если приложение Teams в папке appdata этого пользователя уже установлено, установщик MSI пропускает данную процедуру для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="7a394-116">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="7a394-117">Не используйте MSI для развертывания обновлений, так как клиент обновляется автоматически при обнаружении новой версии в службе.</span><span class="sxs-lookup"><span data-stu-id="7a394-117">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="7a394-118">Чтобы повторно развернуть последний установщик, используйте описанную ниже процедуру для MSI.</span><span class="sxs-lookup"><span data-stu-id="7a394-118">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="7a394-119">Если вы развертываете более старую версию пакета MSI, клиент обновится автоматически, когда это возможно для пользователя.</span><span class="sxs-lookup"><span data-stu-id="7a394-119">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="7a394-120">При развертывании очень старой версии MSI активирует обновление приложения до того, как пользователь может начать работу с Teams.</span><span class="sxs-lookup"><span data-stu-id="7a394-120">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="7a394-121">Мы не рекомендуем изменять расположения установки по умолчанию, так как это может нарушить поток обновления.</span><span class="sxs-lookup"><span data-stu-id="7a394-121">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="7a394-122">Наличие слишком старой версии не позволит пользователям обращаться к службе.</span><span class="sxs-lookup"><span data-stu-id="7a394-122">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-computer-requirements"></a><span data-ttu-id="7a394-123">Требования к целевому компьютеру</span><span class="sxs-lookup"><span data-stu-id="7a394-123">Target computer requirements</span></span>

- <span data-ttu-id="7a394-124">.NET Framework версии 4.5 или более поздней</span><span class="sxs-lookup"><span data-stu-id="7a394-124">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="7a394-125">Windows 7 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="7a394-125">Windows 7 or later</span></span>
- <span data-ttu-id="7a394-126">3 ГБ места на диске для каждого профиля пользователя (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="7a394-126">3 GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="7a394-127">Процедура очистки и повторного развертывания</span><span class="sxs-lookup"><span data-stu-id="7a394-127">Clean up and redeployment procedure</span></span>
<span data-ttu-id="7a394-128">Если пользователь удаляет Teams из своего профиля, установщик MSI регистрирует это и перестает устанавливать Teams для этого профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="7a394-128">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="7a394-129">Чтобы повторно развернуть Teams для этого пользователя на конкретном компьютере, откуда он был удален, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="7a394-129">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="7a394-130">Удалите установленное приложение Teams для каждого профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="7a394-130">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="7a394-131">После удаления рекурсивно удалите каталог, вложенный в %localappdata%\Microsoft\Teams\.</span><span class="sxs-lookup"><span data-stu-id="7a394-131">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span> 
3. <span data-ttu-id="7a394-132">Повторно разверните пакет MSI на этом конкретном компьютере.</span><span class="sxs-lookup"><span data-stu-id="7a394-132">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="7a394-133">Вы можете использовать наш сценарий для [очистки развертывания Microsoft Teams](.\scripts\Powershell-script-teams-deployment-clean-up.md), чтобы выполнить шаги 1 и 2 через SCCM.</span><span class="sxs-lookup"><span data-stu-id="7a394-133">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>                              

