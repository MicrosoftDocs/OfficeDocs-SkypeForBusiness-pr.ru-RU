---
title: 'Поддержка виртуализации Skype для бизнеса Server 2019 '
ms.reviewer: corbinm
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 06/04/20
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Сводка. сведения о поддержке виртуализации в Skype для бизнеса Server 2019.
ms.openlocfilehash: a01f529d80e84df3f7ca844696738b079f78df26
ms.sourcegitcommit: f9db7effbb1e56484686afe4724cc3b73380166d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "44565958"
---
# <a name="virtualization-support-for-skype-for-business-server-2019"></a><span data-ttu-id="6d16f-103">Поддержка виртуализации Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="6d16f-103">Virtualization support for Skype for Business Server 2019</span></span>

<span data-ttu-id="6d16f-104">Skype для бизнеса Server 2019 поддерживается в виртуализации.</span><span class="sxs-lookup"><span data-stu-id="6d16f-104">Skype for Business Server 2019 is supported on virtualization.</span></span>

<span data-ttu-id="6d16f-105">Хотя виртуализация поддерживается, есть некоторые ключевые моменты, которые следует запомнить:</span><span class="sxs-lookup"><span data-stu-id="6d16f-105">While virtualization is supported, there are some key points to remember:</span></span>

- <span data-ttu-id="6d16f-106">Поддерживать 1:1 отношение виртуального ЦП к физическому ЦП.</span><span class="sxs-lookup"><span data-stu-id="6d16f-106">Maintain a 1:1 ratio of virtual CPU to physical CPU.</span></span>
- <span data-ttu-id="6d16f-107">Не перемещайте гостевой сервер во время его работы.</span><span class="sxs-lookup"><span data-stu-id="6d16f-107">Don't move a guest server while it's operating.</span></span>
- <span data-ttu-id="6d16f-108">Миграция действующей системы и переносимость виртуальной машины не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="6d16f-108">Migration of a live system and portability of a virtual machine aren't supported.</span></span>
- <span data-ttu-id="6d16f-109">Отключение технологии Hyper – Threading на всех узлах.</span><span class="sxs-lookup"><span data-stu-id="6d16f-109">Disable hyper-threading on all hosts.</span></span>
- <span data-ttu-id="6d16f-110">Не настраивайте динамическую память на серверах узлов.</span><span class="sxs-lookup"><span data-stu-id="6d16f-110">Don't configure dynamic memory on host servers.</span></span>
- <span data-ttu-id="6d16f-111">Используйте фиксированные или транзитные диски, а не динамические диски.</span><span class="sxs-lookup"><span data-stu-id="6d16f-111">Use fixed or pass-through disks rather than dynamic disks.</span></span>
- <span data-ttu-id="6d16f-112">Разрешите 6-10 процентов для низкоуровневых оболочек, не превышающих требования к виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="6d16f-112">Allow for 6-10 percent overhead for hypervisors beyond what the virtual guest requires.</span></span>

## <a name="supported-hypervisors"></a><span data-ttu-id="6d16f-113">Поддерживаемые низкоуровневые оболочки</span><span class="sxs-lookup"><span data-stu-id="6d16f-113">Supported hypervisors</span></span>

<span data-ttu-id="6d16f-114">SfB Server 2019 поддерживается в Windows Server 2016 и Windows Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6d16f-114">SfB Server 2019 is supported on Windows Server 2016 and Windows Server 2019.</span></span>

<span data-ttu-id="6d16f-115">Для низкоуровневых оболочек необходимы Гипервизоры, которые прошли тестирование программы проверки виртуализации серверов (SVVP) для соответствующей ОС.</span><span class="sxs-lookup"><span data-stu-id="6d16f-115">For third-party hypervisors, you need a hypervisor that has passed the Server Virtualization Validation Program (SVVP) testing for the relevant OS.</span></span>

- <span data-ttu-id="6d16f-116">Ознакомьтесь с [версиями Windows Server 2016](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) , приведенными в списке SVVP.</span><span class="sxs-lookup"><span data-stu-id="6d16f-116">See the [Windows Server 2016 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=88&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
- <span data-ttu-id="6d16f-117">Ознакомьтесь с [версиями Windows Server 2019](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) , приведенными в списке SVVP.</span><span class="sxs-lookup"><span data-stu-id="6d16f-117">See the [Windows Server 2019 versions](https://www.windowsservercatalog.com/results.aspx?&bCatID=1521&cpID=0&avc=86&ava=130&avt=0&avq=0&OR=1&PGS=25) in the SVVP list.</span></span>
