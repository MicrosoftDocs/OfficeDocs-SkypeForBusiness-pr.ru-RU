---
title: Обновления Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/13/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Сведения о том, как обновляется классическое приложение Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0fe542c6df89946ad73f14cf9104f973e292aa3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243846"
---
# <a name="teams-update-process"></a><span data-ttu-id="d5c8b-103">Процесс обновления Teams</span><span class="sxs-lookup"><span data-stu-id="d5c8b-103">Teams update process</span></span>

<span data-ttu-id="d5c8b-104">Веб-приложение Teams обновляется еженедельно.</span><span class="sxs-lookup"><span data-stu-id="d5c8b-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="d5c8b-105">Обновления Teams для настольных систем выпускаются каждые две недели после тщательного внутреннего тестирования и проверки с помощью нашей программы внедрения технологий (TAP).</span><span class="sxs-lookup"><span data-stu-id="d5c8b-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="d5c8b-106">Обычно это происходит во вторник.</span><span class="sxs-lookup"><span data-stu-id="d5c8b-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="d5c8b-107">Если требуется критическое обновление, команды обходят это расписание и отпустите обновление, как только оно станет доступно.</span><span class="sxs-lookup"><span data-stu-id="d5c8b-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="d5c8b-108">Клиент для настольных систем обновится автоматически.</span><span class="sxs-lookup"><span data-stu-id="d5c8b-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="d5c8b-109">Teams проверяет наличие обновлений каждые несколько часов в фоновом режиме, загружает его, а затем ждет бездействия компьютера, прежде чем устанавливать обновление автоматически.</span><span class="sxs-lookup"><span data-stu-id="d5c8b-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="d5c8b-110">Пользователи также могут загружать обновления вручную, щелкнув пункт **Проверка наличия обновлений** в раскрывающемся меню **профиль** в правой верхней части окна приложения.</span><span class="sxs-lookup"><span data-stu-id="d5c8b-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="d5c8b-111">Если обновление доступно, оно будет загружено и автоматически установлено при бездействии компьютера.</span><span class="sxs-lookup"><span data-stu-id="d5c8b-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="d5c8b-112">Для загрузки обновлений пользователи должны войти в систему.</span><span class="sxs-lookup"><span data-stu-id="d5c8b-112">Users need to be signed in for updates to be downloaded.</span></span> 

<span data-ttu-id="d5c8b-113">Начиная с 9 июля 2019 г., после обновления клиенты Teams могут значительно снизить пропускную способность сети.</span><span class="sxs-lookup"><span data-stu-id="d5c8b-113">Starting July 9, 2019, Teams client updates use significantly lower network bandwidth during the update.</span></span> <span data-ttu-id="d5c8b-114">Эта функция включена по умолчанию и не требует никаких действий от администраторов или пользователей.</span><span class="sxs-lookup"><span data-stu-id="d5c8b-114">This is turned on by default and requires no action from admins or users.</span></span>


## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="d5c8b-115">Сведения об обновлениях Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="d5c8b-115">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="d5c8b-116">По умолчанию команды устанавливаются вместе с новыми установками Office 365 ProPlus, как описано в разделе [развертывание Microsoft Teams с Office 365 профессиональный плюс](https://docs.microsoft.com/DeployOffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="d5c8b-116">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="d5c8b-117">В Teams для других приложений Office, таких как Word и Excel, следует процесс обновления, описанный выше, а не процесс обновления.</span><span class="sxs-lookup"><span data-stu-id="d5c8b-117">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="d5c8b-118">Подробнее читайте в статье [Обзор каналов обновления для Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span><span class="sxs-lookup"><span data-stu-id="d5c8b-118">To learn more, read [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="d5c8b-119">Сведения об обновлениях Teams в VDI</span><span class="sxs-lookup"><span data-stu-id="d5c8b-119">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="d5c8b-120">Клиенты Teams в инфраструктуре виртуальных рабочих столов (VDI) не обновляются автоматически так, как клиенты Teams, не связанные с VDI.</span><span class="sxs-lookup"><span data-stu-id="d5c8b-120">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="d5c8b-121">Вы должны обновить образ виртуальной машины установкой нового MSI-файла, как описано в разделе инструкции по [установке Teams в VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span><span class="sxs-lookup"><span data-stu-id="d5c8b-121">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="d5c8b-122">Вы должны удалить текущую версию, чтобы обновить ее до новой версии.</span><span class="sxs-lookup"><span data-stu-id="d5c8b-122">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="d5c8b-123">Могут ли администраторы развертывать обновления вместо автоматического обновления в Teams?</span><span class="sxs-lookup"><span data-stu-id="d5c8b-123">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="d5c8b-124">Teams не предоставляет администраторам возможность развертывать обновления с помощью любого механизма доставки.</span><span class="sxs-lookup"><span data-stu-id="d5c8b-124">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>
