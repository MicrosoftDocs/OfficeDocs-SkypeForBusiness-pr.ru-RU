---
title: Процесс обновления группы
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/13/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Узнайте, обновление клиента рабочего стола группами.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08381341903d21deb42ca83b3769c49f67d18b14
ms.sourcegitcommit: 2449c6dbda4a63aefe5291558cfa41ad7ccf9e39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "33970278"
---
# <a name="teams-update-process"></a><span data-ttu-id="0ec9a-103">Процесс обновления группы</span><span class="sxs-lookup"><span data-stu-id="0ec9a-103">Teams update process</span></span>

<span data-ttu-id="0ec9a-104">Веб-приложения группы обновляется каждую неделю.</span><span class="sxs-lookup"><span data-stu-id="0ec9a-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="0ec9a-105">Команды Настольные клиентские выпуска обновлений через каждые две недели после тщательного внутреннего тестирования и проверки через нашей программы внедрения технологий (TAP).</span><span class="sxs-lookup"><span data-stu-id="0ec9a-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="0ec9a-106">Это обычно выполняется на вторник.</span><span class="sxs-lookup"><span data-stu-id="0ec9a-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="0ec9a-107">При необходимости критические обновления, группами обхода этого расписания и выпуск обновления, как только оно доступно.</span><span class="sxs-lookup"><span data-stu-id="0ec9a-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="0ec9a-108">Клиентское автоматически обновляется.</span><span class="sxs-lookup"><span data-stu-id="0ec9a-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="0ec9a-109">Команды проверяет наличие обновлений каждые несколько часов в фоновом, загружает его и ожидает компьютер в качестве простоя до установки обновления без вмешательства пользователя.</span><span class="sxs-lookup"><span data-stu-id="0ec9a-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="0ec9a-110">Пользователи могут загрузить обновления также вручную, нажав кнопку **Проверить наличие обновлений** в меню раскрывающийся список **профилей** в верхней части окна справа от приложения.</span><span class="sxs-lookup"><span data-stu-id="0ec9a-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="0ec9a-111">Если обновление доступно, его можно было загружено и в тихом режиме во время простоя компьютера.</span><span class="sxs-lookup"><span data-stu-id="0ec9a-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="0ec9a-112">Пользователи должны входить в систему для обновления веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="0ec9a-112">Users need to be signed in for updates to be downloaded.</span></span>

## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="0ec9a-113">Как насчет обновлений для Office 365 ProPlus?</span><span class="sxs-lookup"><span data-stu-id="0ec9a-113">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="0ec9a-114">Группы устанавливается по умолчанию при установке Office 365 профессиональный плюс, как описано в [Развертывание групп Майкрософт с Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span><span class="sxs-lookup"><span data-stu-id="0ec9a-114">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="0ec9a-115">Группам исходя из собственного процесса обновления, как описано выше и не процесс обновления для других приложений офисов, таких как Word и Excel.</span><span class="sxs-lookup"><span data-stu-id="0ec9a-115">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="0ec9a-116">Как насчет обновлений к группам на инфраструктуры виртуальных рабочих СТОЛОВ?</span><span class="sxs-lookup"><span data-stu-id="0ec9a-116">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="0ec9a-117">Группы клиентов на инфраструктуры виртуальных рабочих столов (VDI) не обновляются автоматически способа, которые клиенты групп, не являющиеся инфраструктуры виртуальных рабочих СТОЛОВ.</span><span class="sxs-lookup"><span data-stu-id="0ec9a-117">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="0ec9a-118">Необходимо обновить образ виртуальной Машины путем установки нового MSI, как описано в инструкциях по [Командам инфраструктуры виртуальных рабочих СТОЛОВ, установка](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span><span class="sxs-lookup"><span data-stu-id="0ec9a-118">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="0ec9a-119">Необходимо удалить текущую версию, чтобы обновление до новой версии.</span><span class="sxs-lookup"><span data-stu-id="0ec9a-119">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="0ec9a-120">Можно "Администраторы" развертывание обновлений вместо команды Автоматическое обновление?</span><span class="sxs-lookup"><span data-stu-id="0ec9a-120">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="0ec9a-121">Группы не предоставляют возможность развертывания обновлений каким-либо способом доставки "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="0ec9a-121">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>
