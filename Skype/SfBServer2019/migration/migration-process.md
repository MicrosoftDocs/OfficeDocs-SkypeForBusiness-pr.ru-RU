---
title: Процесс миграции
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Рекомендуемая и поддерживаемая процедура миграции в Skype для бизнеса Server 2019 является параллельной миграцией. В этой статье описаны причины, по которым следует использовать параллельную миграцию, а также сведения о проверке сосуществования.
ms.openlocfilehash: 7d8ce6513535871939894092850ad0526b1b6a63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813417"
---
# <a name="migration-process"></a><span data-ttu-id="1f0ec-104">Процесс миграции</span><span class="sxs-lookup"><span data-stu-id="1f0ec-104">Migration process</span></span>

<span data-ttu-id="1f0ec-105">Рекомендуемая и поддерживаемая процедура миграции в Skype для бизнеса Server 2019 является параллельной миграцией.</span><span class="sxs-lookup"><span data-stu-id="1f0ec-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="1f0ec-106">В этой статье описаны причины, по которым следует использовать параллельную миграцию, а также сведения о проверке сосуществования.</span><span class="sxs-lookup"><span data-stu-id="1f0ec-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="1f0ec-107">Переход с одной стороны на другую</span><span class="sxs-lookup"><span data-stu-id="1f0ec-107">Side-By-Side Migration</span></span>

<span data-ttu-id="1f0ec-108">Почти во всех случаях миграции следует использовать путь параллельной миграции.</span><span class="sxs-lookup"><span data-stu-id="1f0ec-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="1f0ec-109">При переходе по отдельности вы развертываете новый сервер с помощью Skype для бизнеса Server 2019 вместе с соответствующим сервером, на котором запущена предыдущая версия, а затем перенесите операции на новый сервер.</span><span class="sxs-lookup"><span data-stu-id="1f0ec-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="1f0ec-110">Если вы хотите вернуться к предыдущей версии, вы можете только переместить операции обратно на первоначальные серверы.</span><span class="sxs-lookup"><span data-stu-id="1f0ec-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="1f0ec-111">Имейте в виду, что в этом случае новые собрания, запланированные на обновленных клиентах, не будут работать, а клиентам также потребуется понизить уровень.</span><span class="sxs-lookup"><span data-stu-id="1f0ec-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="1f0ec-112">Тестирование сосуществования</span><span class="sxs-lookup"><span data-stu-id="1f0ec-112">Coexistence Testing</span></span>

<span data-ttu-id="1f0ec-113">После развертывания Skype для бизнеса Server 2019 параллельно с предыдущей версией развертывание представляет состояние тестирования сосуществования Skype для бизнеса Server 2019 и предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="1f0ec-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="1f0ec-114">В этом состоянии важно проверить и убедиться, что службы запущены, можно администрировать каждый сайт, а клиенты смогут общаться с текущими и устаревшими пользователями.</span><span class="sxs-lookup"><span data-stu-id="1f0ec-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="1f0ec-115">Прежде чем переходить от всех пользователей, очень важно понять состояние каждого развертывания и убедиться, что каждое развертывание работает и работает правильно.</span><span class="sxs-lookup"><span data-stu-id="1f0ec-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="1f0ec-116">Как правило, этап тестирования сосуществования используется во время пилотного тестирования Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1f0ec-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="1f0ec-117">Пользователи прежних версий перемещаются в Skype для бизнеса Server 2019 в течение определенного периода времени, чтобы убедиться в том, что совместимость приложений и функции и возможности работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="1f0ec-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="1f0ec-118">После пилотной проверки пользователи и приложения перемещаются в производственную версию Skype для бизнеса Server 2019, а устаревшие пулы и приложения предыдущей версии будут прекращены.</span><span class="sxs-lookup"><span data-stu-id="1f0ec-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
