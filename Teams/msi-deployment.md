---
title: Установка группами Майкрософт, с помощью MSI
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: Администраторы могут использовать команды MSI для массового развертывания групп Майкрософт для выбора пользователей или компьютеров.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e8d1f8b77b4b362b95fb03d3f0202bfc6da619e8
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="f84a1-103">Установка группами Майкрософт, с помощью MSI</span><span class="sxs-lookup"><span data-stu-id="f84a1-103">Install Microsoft Teams using MSI</span></span>
===========================================

<span data-ttu-id="f84a1-104">Чтобы использовать для широкомасштабного развертывания решения System Center Configuration Manager или групповой политики или любой механизмы рассылки сторонних производителей, корпорация Майкрософт предоставляет файлов MSI ( [32-разрядная](http://aka.ms/teams32bitmsi) и [64-разрядная версия](http://aka.ms/teams64bitmsi)), администраторы могут использовать для развертывания массового рабочих групп для выбора пользователи и компьютеры.</span><span class="sxs-lookup"><span data-stu-id="f84a1-104">To use System Center Configuration Manager, or Group Policy, or any 3rd party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](http://aka.ms/teams32bitmsi) and [64-bit](http://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or machines.</span></span> <span data-ttu-id="f84a1-105">Администраторы могут использовать эти файлы для удаленного развертывания групп, чтобы пользователи не имеют для ручной загрузки приложения группы.</span><span class="sxs-lookup"><span data-stu-id="f84a1-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="f84a1-106">При развертывании команды будет автоматически запуска для всех пользователей, вход на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="f84a1-106">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="f84a1-107">Мы рекомендуем развертывания пакета на компьютере, поэтому всех новых пользователей компьютера также выиграют от этого развертывания.</span><span class="sxs-lookup"><span data-stu-id="f84a1-107">We recommend that you deploy the package to the machine, so all new users of the machine will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="f84a1-108">Чтобы узнать больше о SCCM, см [В System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="f84a1-108">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="f84a1-109">Процедуры развертывания (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="f84a1-109">Deployment Procedure (Recommended)</span></span>
1. <span data-ttu-id="f84a1-110">Получить последнюю версию пакета</span><span class="sxs-lookup"><span data-stu-id="f84a1-110">Retrieve the latest package</span></span>
2. <span data-ttu-id="f84a1-111">Используйте параметры по умолчанию, предварительно с MSI-файла</span><span class="sxs-lookup"><span data-stu-id="f84a1-111">Use the defaults prepopulated by the MSI</span></span>
3. <span data-ttu-id="f84a1-112">Развертывания на компьютерах, когда это возможно</span><span class="sxs-lookup"><span data-stu-id="f84a1-112">Deploy to machines when possible</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="f84a1-113">Как работает пакет MSI группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f84a1-113">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="f84a1-114">MSI группы будут помещены установщика в Program Files.</span><span class="sxs-lookup"><span data-stu-id="f84a1-114">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="f84a1-115">Каждый раз, когда пользователь входит в новый профиль пользователя Windows, запускается программа установки и копию приложения группы должны устанавливаться в папку appdata этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="f84a1-115">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="f84a1-116">Если пользователь уже имеет приложения группы, устанавливается в папку appdata, установщик MSI пропустит процесс для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="f84a1-116">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="f84a1-117">Не используйте MSI-файла для развертывания обновлений, клиент будет автоматически обновления, когда обнаруживает, что новая версия, доступные в службе.</span><span class="sxs-lookup"><span data-stu-id="f84a1-117">Do not use the MSI to deploy updates, the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="f84a1-118">Повторное развертывание последние установщик использовать процесс повторное развертывание MSI описано ниже.</span><span class="sxs-lookup"><span data-stu-id="f84a1-118">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="f84a1-119">При развертывании более старые версии пакета MSI, клиент будет автоматическое обновление по возможности для пользователя.</span><span class="sxs-lookup"><span data-stu-id="f84a1-119">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="f84a1-120">Если очень старой версии получает развернут, MSI-файла будет активировано обновления приложения, прежде чем пользователь сможет использовать команды.</span><span class="sxs-lookup"><span data-stu-id="f84a1-120">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="f84a1-121">Не рекомендуется изменить расположения установки по умолчанию, как это может нарушить этот процесс обновления.</span><span class="sxs-lookup"><span data-stu-id="f84a1-121">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="f84a1-122">Наличие слишком старой версии со временем блокировать пользователям доступ к службе.</span><span class="sxs-lookup"><span data-stu-id="f84a1-122">Having too old a version will eventually block users from accessing the service.</span></span> 


## <a name="target-machine-requirements"></a><span data-ttu-id="f84a1-123">Требования к конечного компьютера</span><span class="sxs-lookup"><span data-stu-id="f84a1-123">Target machine requirements</span></span>

1. <span data-ttu-id="f84a1-124">.NET framework 4.5 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="f84a1-124">.NET framework 4.5 or later</span></span>
2. <span data-ttu-id="f84a1-125">Windows 7 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="f84a1-125">Windows 7 or later</span></span>
2. <span data-ttu-id="f84a1-126">3 ГБ дискового пространства для каждого профиля пользователя (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="f84a1-126">3GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="f84a1-127">Очистить копии и повторного развертывания процедуры</span><span class="sxs-lookup"><span data-stu-id="f84a1-127">Clean up and redeployment Procedure</span></span>
<span data-ttu-id="f84a1-128">Если пользователь удаляет команды из своего профиля пользователя, установщик MSI будет отслеживать, что пользователь отменил установку приложения группы и больше не установить групп для этого профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="f84a1-128">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="f84a1-129">Повторное развертывание групп для этого пользователя на определенном компьютере, где она была удалена, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f84a1-129">To redeploy Teams for this user on a particular machine where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="f84a1-130">Удаление группы приложения, установленные для каждого профиля пользователя</span><span class="sxs-lookup"><span data-stu-id="f84a1-130">Uninstall Teams App installed for every user profile</span></span> 
2. <span data-ttu-id="f84a1-131">После удаления, удалите рекурсивно каталога в разделе %localappdata%\Microsoft\Teams\\</span><span class="sxs-lookup"><span data-stu-id="f84a1-131">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\\</span></span> 
3. <span data-ttu-id="f84a1-132">Повторное развертывание пакета MSI на конкретном компьютере</span><span class="sxs-lookup"><span data-stu-id="f84a1-132">Redeploy the MSI package to that particular machine</span></span>

> [!TIP] 
> <span data-ttu-id="f84a1-133">Наш сценарий [развертывания групп Майкрософт Очистка](.\scripts\Powershell-script-teams-deployment-clean-up.md) можно использовать для выполнения действия 1 и 2 с помощью SCCM.</span><span class="sxs-lookup"><span data-stu-id="f84a1-133">You can use our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>                              

