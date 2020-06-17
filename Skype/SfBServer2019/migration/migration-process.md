---
title: Процесс миграции
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Рекомендуемая и поддерживаемая процедура миграции для Skype для бизнеса Server 2019 — параллельная миграция. В этом разделе описывается, почему следует использовать параллельную миграцию, а также сведения о тестировании сосуществования.
ms.openlocfilehash: 2343e3d6dd7eadbcfbf2b900d51594253e22f933
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752641"
---
# <a name="migration-process"></a><span data-ttu-id="5b99f-104">Процесс миграции</span><span class="sxs-lookup"><span data-stu-id="5b99f-104">Migration process</span></span>

<span data-ttu-id="5b99f-105">Рекомендуемая и поддерживаемая процедура миграции для Skype для бизнеса Server 2019 — параллельная миграция.</span><span class="sxs-lookup"><span data-stu-id="5b99f-105">The recommended and supported migration procedure for Skype for Business Server 2019 is side-by-side migration.</span></span> <span data-ttu-id="5b99f-106">В этом разделе описывается, почему следует использовать параллельную миграцию, а также сведения о тестировании сосуществования.</span><span class="sxs-lookup"><span data-stu-id="5b99f-106">This topic describes why you should use side-by-side migration and also includes information about coexistence testing.</span></span>
  
## <a name="side-by-side-migration"></a><span data-ttu-id="5b99f-107">Параллельная миграция</span><span class="sxs-lookup"><span data-stu-id="5b99f-107">Side-By-Side Migration</span></span>

<span data-ttu-id="5b99f-108">Почти во всех случаях следует использовать параллельную миграцию.</span><span class="sxs-lookup"><span data-stu-id="5b99f-108">In nearly every migration, you should use the side-by-side migration path.</span></span> <span data-ttu-id="5b99f-109">При параллельной миграции вы развертываете новый сервер со Skype для бизнеса Server 2019 вместе с соответствующим сервером, на котором выполняется предыдущая версия, а затем перенесите операции на новый сервер.</span><span class="sxs-lookup"><span data-stu-id="5b99f-109">In a side-by-side migration, you deploy a new server with Skype for Business Server 2019 alongside a corresponding server that is running a previous version, and then transfer operations to the new server.</span></span> <span data-ttu-id="5b99f-110">Если потребуется выполнить откат к предыдущей версии, только переместит операции обратно на исходные серверы.</span><span class="sxs-lookup"><span data-stu-id="5b99f-110">If it becomes necessary to roll back to the previous version, you have only to shift operations back to the original servers.</span></span> <span data-ttu-id="5b99f-111">Имейте в виду, что в этом случае проведение новых собраний, запланированных с помощью обновленных клиентов, будет невозможно, и клиенты также потребуется откатить до предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="5b99f-111">Be aware that in this situation any new meetings scheduled with upgraded clients will not work, and the clients would also need to be downgraded.</span></span>
  
## <a name="coexistence-testing"></a><span data-ttu-id="5b99f-112">Тестирование сосуществования</span><span class="sxs-lookup"><span data-stu-id="5b99f-112">Coexistence Testing</span></span>

<span data-ttu-id="5b99f-113">После развертывания Skype для бизнеса Server 2019 параллельно с предыдущей версией развертывание представляет состояние тестирования сосуществования Skype для бизнеса Server 2019 и предыдущей версии.</span><span class="sxs-lookup"><span data-stu-id="5b99f-113">After you have deployed Skype for Business Server 2019 in parallel with the previous version, the deployment represents a coexistence testing state of Skype for Business Server 2019 and the previous version.</span></span> <span data-ttu-id="5b99f-114">В этом состоянии важно проверить и убедиться, что службы запущены, можно администрировать каждый сайт, а клиенты могут общаться с текущими и устаревшими пользователями.</span><span class="sxs-lookup"><span data-stu-id="5b99f-114">While in this state, it is important to test and ensure that services are started, each site can be administered, and clients can communicate with current and legacy users.</span></span> <span data-ttu-id="5b99f-115">Перед миграцией всех пользователей крайне важно оценить состояние каждого развертывания и убедиться в его работоспособности.</span><span class="sxs-lookup"><span data-stu-id="5b99f-115">Prior to the migration of all users, it is very important that you understand the state of each deployment and ensure that each deployment is functional and working properly.</span></span> <span data-ttu-id="5b99f-116">Как правило, этап тестирования сосуществования существует во время пилотного тестирования Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5b99f-116">Typically, the coexistence testing phase exists throughout the pilot testing of Skype for Business Server 2019.</span></span> <span data-ttu-id="5b99f-117">Устаревшие пользователи перемещаются в Skype для бизнеса Server 2019 в течение определенного периода времени, чтобы убедиться, что совместимость и функции и функции приложения работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="5b99f-117">Legacy users are moved to Skype for Business Server 2019 for a period of time to ensure that application compatibility and features and functions are working properly.</span></span> <span data-ttu-id="5b99f-118">После пилотного тестирования пользователи и приложения переносятся в рабочую версию Skype для бизнеса Server 2019, а устаревшие пулы и приложения предыдущей версии будут отменены.</span><span class="sxs-lookup"><span data-stu-id="5b99f-118">After pilot testing, users and applications are moved to the production version of Skype for Business Server 2019, and the legacy pools and applications of the previous version are retired.</span></span>
  
