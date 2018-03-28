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
ms.openlocfilehash: 4b092403be87eb4e87b058ba0e7363d5f2d691f4
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="626e1-103">Установка группами Майкрософт, с помощью MSI</span><span class="sxs-lookup"><span data-stu-id="626e1-103">Install Microsoft Teams using MSI</span></span>
===========================================

<span data-ttu-id="626e1-104">Внедрить с помощью System Center Configuration Manager или групповой политики или любой механизмы сторонних производителей рассылки широкомасштабного развертывания решения, корпорация Майкрософт предоставляет MSI-файлы ( [32-разрядная](http://aka.ms/teams32bitmsi) и [64-разрядная версия](http://aka.ms/teams64bitmsi)) для администраторов для использования во время массового развертывания Группами Майкрософт для выбора пользователей или компьютеров.</span><span class="sxs-lookup"><span data-stu-id="626e1-104">To leverage System Center Configuration Manager, or Group Policy, or any 3rd party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](http://aka.ms/teams32bitmsi) and [64-bit](http://aka.ms/teams64bitmsi)) for admins to leverage during bulk deployment of Microsoft Teams to select users or machines.</span></span> <span data-ttu-id="626e1-105">Администраторы могут использовать эти файлы для удаленного развертывания групп, чтобы пользователи не имеют для ручной загрузки приложения группы.</span><span class="sxs-lookup"><span data-stu-id="626e1-105">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="626e1-106">При развертывании команды будет автоматически запуска для всех пользователей, вход на этом компьютере.</span><span class="sxs-lookup"><span data-stu-id="626e1-106">When deployed, Teams will auto launch for all users who sign-in on that machine.</span></span> <span data-ttu-id="626e1-107">Рекомендуется развертывания пакета на компьютере, поэтому всех новых пользователей на компьютерах также выиграют от этого развертывания.</span><span class="sxs-lookup"><span data-stu-id="626e1-107">It is recommended that you deploy the package to the machine, so all new users to the machines will also benefit from this deployment.</span></span> 
 
> [!Note] 
> <span data-ttu-id="626e1-108">Чтобы узнать больше о SCCM, обратитесь к разделу.</span><span class="sxs-lookup"><span data-stu-id="626e1-108">To learn more about SCCM, see.</span></span> [<span data-ttu-id="626e1-109">Введение в System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="626e1-109">Introduction to System Center Configuration Manager</span></span>](https://docs.microsoft.com/sccm/core/understand/introduction)

## <a name="deployment-procedure-recommendations"></a><span data-ttu-id="626e1-110">Процедуры развертывания (рекомендации)</span><span class="sxs-lookup"><span data-stu-id="626e1-110">Deployment Procedure (Recommendations)</span></span>
1. <span data-ttu-id="626e1-111">Получить последнюю версию пакета</span><span class="sxs-lookup"><span data-stu-id="626e1-111">Retrieve the latest package</span></span>
2. <span data-ttu-id="626e1-112">Используйте параметры по умолчанию, предварительно с MSI-файла</span><span class="sxs-lookup"><span data-stu-id="626e1-112">Use the defaults prepopulated by the MSI</span></span>
3. <span data-ttu-id="626e1-113">Развертывания на компьютерах, когда это возможно</span><span class="sxs-lookup"><span data-stu-id="626e1-113">Deploy to machines when possible</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="626e1-114">Как работает пакет MSI группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="626e1-114">How the Microsoft Teams MSI package works</span></span>

<span data-ttu-id="626e1-115">MSI группы будут помещены установщика в Program Files.</span><span class="sxs-lookup"><span data-stu-id="626e1-115">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="626e1-116">Каждый раз, когда пользователь входит в новый профиль пользователя Windows, запускается программа установки и копию приложения группы должны устанавливаться в папку appdata этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="626e1-116">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of Teams application will be installed in that user's appdata folder.</span></span> <span data-ttu-id="626e1-117">Если пользователь уже имеет приложения группы, устанавливается в папку appdata, установщик MSI пропустит процесс для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="626e1-117">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="626e1-118">Не используйте MSI для развертывания обновлений, клиент будет автоматически обновления, когда обнаруживает, что новая версия, доступные в службе.</span><span class="sxs-lookup"><span data-stu-id="626e1-118">Do not leverage the MSI to deploy updates, the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="626e1-119">Повторное развертывание последние установщик использовать процесс повторное развертывание MSI описано ниже.</span><span class="sxs-lookup"><span data-stu-id="626e1-119">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="626e1-120">При развертывании более старые версии пакета MSI, клиент будет автоматическое обновление по возможности для пользователя.</span><span class="sxs-lookup"><span data-stu-id="626e1-120">If you deploy an older version of the MSI package, the client will auto-update when possible for the user.</span></span> <span data-ttu-id="626e1-121">Если очень старой версии получает развернут, MSI-файла будет активировано обновления приложения, прежде чем пользователь сможет использовать команды.</span><span class="sxs-lookup"><span data-stu-id="626e1-121">If a very old version gets deployed, the MSI will trigger an application update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="626e1-122">Не рекомендуется изменять любого расположения установки, как это может нарушить этот процесс обновления.</span><span class="sxs-lookup"><span data-stu-id="626e1-122">It's not recommended you change any install locations as this could break the update flow.</span></span> <span data-ttu-id="626e1-123">Затем которого со временем блокирует пользователям доступ к службе.</span><span class="sxs-lookup"><span data-stu-id="626e1-123">Which then will eventually block users from accessing the service.</span></span> 


## <a name="target-machine-requirements"></a><span data-ttu-id="626e1-124">Требования к конечного компьютера:</span><span class="sxs-lookup"><span data-stu-id="626e1-124">Target machine requirements:</span></span>

1. <span data-ttu-id="626e1-125">.NET framework 4.5 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="626e1-125">.NET framework 4.5 or later</span></span>
2. <span data-ttu-id="626e1-126">Windows 7 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="626e1-126">Windows 7 or later</span></span>
2. <span data-ttu-id="626e1-127">32 ГБ дискового пространства для каждого профиля пользователя (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="626e1-127">32GB of disk space for each user profile (recommended)</span></span>

## <a name="clean-upredeployment-procedure"></a><span data-ttu-id="626e1-128">Очистить up\redeployment процедуры</span><span class="sxs-lookup"><span data-stu-id="626e1-128">Clean up\redeployment Procedure</span></span>
<span data-ttu-id="626e1-129">Если пользователь удаляет групп из для своего профиля пользователя, установщик MSI будет отслеживать, что пользователь отменил установку приложения группы и больше не установить групп для этого профиля пользователя.</span><span class="sxs-lookup"><span data-stu-id="626e1-129">If a user uninstalls Teams from for their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="626e1-130">Повторное развертывание групп для этого пользователя на определенном компьютере, где он был удален, вам потребуется:</span><span class="sxs-lookup"><span data-stu-id="626e1-130">To redeploy Teams for this user on a particular machine where it was uninstalled you will need to:</span></span>

1. <span data-ttu-id="626e1-131">Удаление группы приложения, установленные для каждого профиля пользователя</span><span class="sxs-lookup"><span data-stu-id="626e1-131">Uninstall Teams App installed for every user profile</span></span> 
2. <span data-ttu-id="626e1-132">После удаления, удалите рекурсивно каталога в разделе %localappdata%\Microsoft\Teams\\</span><span class="sxs-lookup"><span data-stu-id="626e1-132">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\\</span></span> 
3. <span data-ttu-id="626e1-133">Повторное развертывание пакета MSI на конкретном компьютере</span><span class="sxs-lookup"><span data-stu-id="626e1-133">Redeploy the MSI package to that particular machine</span></span>

> [!TIP] 
> <span data-ttu-id="626e1-134">Вы можете использовать возможности наших [Очистка развертывания групп Майкрософт](.\scripts\Powershell-script-teams-deployment-clean-up.md) скрипта для выполнения этого действия 1 и 2 с помощью SCCM.</span><span class="sxs-lookup"><span data-stu-id="626e1-134">You can leverage our [Microsoft Teams deployment clean up](.\scripts\Powershell-script-teams-deployment-clean-up.md) script to accomplish this steps 1 and 2 via SCCM.</span></span>                                

