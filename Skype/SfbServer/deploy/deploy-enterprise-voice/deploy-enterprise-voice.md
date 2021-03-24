---
title: Развертывание Корпоративная голосовая связь в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: Сводка. Сведения о развертывании Корпоративная голосовая связь Skype для бизнес-сервера на центральном сайте.
ms.openlocfilehash: c2aead4d42a02acce6b0db9f92866dba3a6e956d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104975"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="7bdfe-103">Развертывание Корпоративная голосовая связь в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7bdfe-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="7bdfe-104">**Сводка:** Узнайте, как развернуть Корпоративная голосовая связь Skype для бизнеса Server на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="7bdfe-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="7bdfe-105">Используйте эту тему для развертывания Корпоративная голосовая связь на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="7bdfe-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="7bdfe-106">Чтобы развернуть Корпоративная голосовая связь на сайте филиала, пропустите [развертывание сайтов филиалов.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-branch-sites)</span><span class="sxs-lookup"><span data-stu-id="7bdfe-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-branch-sites).</span></span>

<span data-ttu-id="7bdfe-107">В этом разделе содержатся процедуры развертывания, в которых сервер-посредник находится на каждом сервере переднего или стандартного выпуска, как рекомендуется, а также для развертывания с автономным пулом серверов-посредников. Вы можете пропустить следующий контент, если вы использовали Topology Builder для определения и публикации топологии, которая коллокирует сервер-посредник на каждом сервере переднего или стандартного выпуска, так как мастер развертывания уже автоматически установил файлы для сервера-посредника при установке файлов для пула переднего конечного сервера или сервера Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="7bdfe-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="7bdfe-108">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="7bdfe-108">In this section</span></span>

- [<span data-ttu-id="7bdfe-109">Необходимые условия безопасности и конфигурации для Корпоративная голосовая связь Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7bdfe-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="7bdfe-110">Развертывание сервера-посредника в topology Builder в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7bdfe-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="7bdfe-111">Определение шлюза в Topology Builder в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7bdfe-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="7bdfe-112">Определение дополнительных магистральных магистрали в Topology Builder в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7bdfe-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="7bdfe-113">Установка файлов для сервера-посредника в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7bdfe-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="7bdfe-114">Настройка магистральных серверов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7bdfe-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="7bdfe-115">Создание или изменение правила перевода для представления ID вызываемой звонков в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7bdfe-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="7bdfe-116">Создание или изменение правила перевода для так называемой презентации ID в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7bdfe-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="7bdfe-117">Создание или изменение правила нормализации в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7bdfe-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="7bdfe-118">Создание или изменение набора номера в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7bdfe-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="7bdfe-119">Настройка голосовых политик, записей использования PSTN и голосовых маршрутов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7bdfe-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="7bdfe-120">Включить пользователей для Корпоративная голосовая связь в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7bdfe-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="7bdfe-121">Развертывание расширенных Корпоративная голосовая связь в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7bdfe-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="7bdfe-122">Развертывание функций управления вызовами в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7bdfe-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="7bdfe-123">См. также</span><span class="sxs-lookup"><span data-stu-id="7bdfe-123">See also</span></span>

[<span data-ttu-id="7bdfe-124">Планирование Корпоративная голосовая связь в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7bdfe-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)