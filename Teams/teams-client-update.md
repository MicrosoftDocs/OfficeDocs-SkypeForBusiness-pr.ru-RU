---
title: Teams обновлений
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: В этой статье вы узнаете, как обновить клиент Microsoft Teams компьютеров.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 004c615d2b624f4e5942562e6abfed6e1aebf7cd
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717900"
---
# <a name="teams-update-process"></a><span data-ttu-id="7db06-103">Teams обновления</span><span class="sxs-lookup"><span data-stu-id="7db06-103">Teams update process</span></span>

<span data-ttu-id="7db06-104">Веб-Teams обновляется еженедельно.</span><span class="sxs-lookup"><span data-stu-id="7db06-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="7db06-105">Teams обновлений для настольных пк выпускаются каждые две недели после строгого внутреннего тестирования и проверки в рамках программы внедрения технологий (TAP).</span><span class="sxs-lookup"><span data-stu-id="7db06-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="7db06-106">Обновление обычно происходит во вторник.</span><span class="sxs-lookup"><span data-stu-id="7db06-106">The update usually takes place on a Tuesday.</span></span> <span data-ttu-id="7db06-107">Если требуется критическое обновление, Teams обошел это расписание и отпустит обновление, как только оно станет доступно.</span><span class="sxs-lookup"><span data-stu-id="7db06-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="7db06-108">Клиент для настольных компьютеров обновляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="7db06-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="7db06-109">Teams проверяет наличие обновлений каждые несколько часов в сети, скачивает их, а затем ждет, пока компьютер не будет простаивать, прежде чем устанавливать обновление автоматически.</span><span class="sxs-lookup"><span data-stu-id="7db06-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="7db06-110">Пользователи также могут скачивать обновления  вручную, выбрав  Проверить обновления в меню Профиль в правой верхней части приложения.</span><span class="sxs-lookup"><span data-stu-id="7db06-110">Users can also manually download updates by selecting **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="7db06-111">Если обновление доступно, оно скачивается и автоматически устанавливается, когда компьютер простаивает.</span><span class="sxs-lookup"><span data-stu-id="7db06-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="7db06-112">Для скачивания обновлений пользователям необходимо вошел в нее.</span><span class="sxs-lookup"><span data-stu-id="7db06-112">Users need to be signed in for updates to be downloaded.</span></span>

<span data-ttu-id="7db06-113">Начиная с 31 июля 2019 г., Teams обновления клиента используют низкую пропускную способность сети во время обновления.</span><span class="sxs-lookup"><span data-stu-id="7db06-113">Starting July 31, 2019, Teams client updates use lower network bandwidth during the update.</span></span> <span data-ttu-id="7db06-114">Это обновление включено по умолчанию и не требует действий от администраторов и пользователей.</span><span class="sxs-lookup"><span data-stu-id="7db06-114">This update is turned on by default and requires no action from admins or users.</span></span>

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="7db06-115">Как насчет обновлений Приложения Microsoft 365 для предприятий?</span><span class="sxs-lookup"><span data-stu-id="7db06-115">What about updates to Microsoft 365 Apps for enterprise?</span></span>

<span data-ttu-id="7db06-116">Teams устанавливается по умолчанию вместе с новыми Приложения Microsoft 365 для предприятий, как описано в Microsoft Teams [развертывании Приложения Microsoft 365 для предприятий](/DeployOffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="7db06-116">Teams is installed by default with new installations of Microsoft 365 Apps for enterprise as described in [Deploy Microsoft Teams with Microsoft 365 Apps for enterprise](/DeployOffice/teams-install).</span></span>

<span data-ttu-id="7db06-117">Teams собственным процессом обновления, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="7db06-117">Teams follows its own update process as outlined above.</span></span> <span data-ttu-id="7db06-118">Teams не обновляет другие приложения Office, такие как Word и Excel.</span><span class="sxs-lookup"><span data-stu-id="7db06-118">Teams doesn't follow the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="7db06-119">Дополнительные сведения можно найти в [обзоре каналов](/DeployOffice/overview-of-update-channels-for-office-365-proplus) обновления для Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="7db06-119">To learn more, read [Overview of update channels for Microsoft 365 Apps for enterprise](/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="7db06-120">Как насчет обновлений Teams VDI?</span><span class="sxs-lookup"><span data-stu-id="7db06-120">What about updates to Teams on VDI?</span></span>


<span data-ttu-id="7db06-121">Teams клиентах инфраструктура виртуальных рабочих столов (VDI) не обновляются автоматически в том же Teams VDI.</span><span class="sxs-lookup"><span data-stu-id="7db06-121">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="7db06-122">Вам нужно обновить изображение VM, установив новый MSI-версию, как описано в инструкциях по установке Teams [на VDI.](teams-for-vdi.md)</span><span class="sxs-lookup"><span data-stu-id="7db06-122">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](teams-for-vdi.md).</span></span> <span data-ttu-id="7db06-123">Чтобы обновить текущую версию, необходимо удалить текущую версию.</span><span class="sxs-lookup"><span data-stu-id="7db06-123">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="7db06-124">Могут ли администраторы развертывать обновления вместо автоматического Teams обновления?</span><span class="sxs-lookup"><span data-stu-id="7db06-124">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="7db06-125">Teams не дает администраторам возможность развертывать обновления с помощью любого механизма доставки.</span><span class="sxs-lookup"><span data-stu-id="7db06-125">Teams doesn't give admins the ability to deploy updates through any delivery mechanism.</span></span>

## <a name="servicing-agreement"></a><span data-ttu-id="7db06-126">Соглашение об обслуживании</span><span class="sxs-lookup"><span data-stu-id="7db06-126">Servicing agreement</span></span>

<span data-ttu-id="7db06-127">Как современная веб-служба клиент Teams обновляется каждые две недели.</span><span class="sxs-lookup"><span data-stu-id="7db06-127">As a modern online service, the Teams client auto-updates every two weeks.</span></span> <span data-ttu-id="7db06-128">Так Teams управляется современной политикой жизненного цикла, предполагается, что пользователи остаются на самой новой версии клиента для настольных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="7db06-128">Because Teams is governed by the Modern Lifecycle Policy, it's expected that users remain on the most up-to-date version of the desktop client.</span></span> <span data-ttu-id="7db06-129">Автоматическое обновление обеспечивает пользователям новейшие возможности, улучшения производительности, безопасности и надежности служб.</span><span class="sxs-lookup"><span data-stu-id="7db06-129">Auto-updates ensure that users have the latest capabilities, performance enhancements, security, and service reliability.</span></span>

<span data-ttu-id="7db06-130">Чтобы определить, когда клиенты для настольных компьютеров устарели, в приложении отображается оповещение о том, что текущая версия пользователя находится в периоде от одного до трех месяцев и доступна ли новая версия.</span><span class="sxs-lookup"><span data-stu-id="7db06-130">To identify when desktop clients fall out of date, an in-app alert will be displayed if the user’s current version is between one and three months old, and if there's a new version available.</span></span> <span data-ttu-id="7db06-131">Такое сообщение в приложении позволяет пользователям обновить приложение до последней версии Teams или при необходимости связаться со своим ИТ-администратором.</span><span class="sxs-lookup"><span data-stu-id="7db06-131">This in-app messaging encourages users to update to the latest version of Teams or, if necessary, to reach out to their IT admin to do so.</span></span> <span data-ttu-id="7db06-132">Пользователи классических Teams, у которых более трех месяцев, увидят страницу блокировки, на которую можно обновить обновления, связаться со своим ИТ-администратором или продолжить Teams в Интернете.</span><span class="sxs-lookup"><span data-stu-id="7db06-132">Users on Teams desktop clients that are more than three months old will see a blocking page that gives the options to update now, reach out to their IT admin, or continue to Teams on the web.</span></span>

<span data-ttu-id="7db06-133">Teams клиенты на облачных устройствах государственных служб в настоящее время имеют исключение из этого соглашения об обслуживании до получения дополнительных уведомлений.</span><span class="sxs-lookup"><span data-stu-id="7db06-133">Teams desktop clients on Government Clouds currently have an exception to this servicing agreement until further notice.</span></span>

<span data-ttu-id="7db06-134">Сведения о новых версиях можно найти в Центре [сообщений](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) или в **справке** о новых  >   клиентах.</span><span class="sxs-lookup"><span data-stu-id="7db06-134">For information on new version releases, check [Message Center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) or go to **Help** > **What’s new** in the client.</span></span>
