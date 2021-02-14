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
description: Сводка. Сведения о развертывании Корпоративная голосовая связь Skype для бизнеса Server на центральном сайте.
ms.openlocfilehash: 246c1e5c03401b885b297ada08677fb40faad60d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812499"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="35ceb-103">Развертывание Корпоративная голосовая связь в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="35ceb-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="35ceb-104">**Сводка:** Узнайте, как развернуть Корпоративная голосовая связь Skype для бизнеса Server на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="35ceb-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="35ceb-105">Используйте этот раздел для развертывания Корпоративная голосовая связь на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="35ceb-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="35ceb-106">Чтобы развернуть Корпоративная голосовая связь на сайте филиала, переперейти к [развертыванию сайтов филиалов.](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx)</span><span class="sxs-lookup"><span data-stu-id="35ceb-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="35ceb-107">В этом разделе содержатся процедуры развертывания, в которых сервер-посредник размещен на каждом сервере переднего сервера или сервере Standard Edition ( рекомендуется), а также для развертывания с автономным пулом серверов-посредников. Если вы использовали построитель топологий для определения и публикации топологии, которая размещена на сервере-посреднике на каждом сервере переднего сервера или сервере Standard Edition, можно пропустить следующее содержимое, так как мастер развертывания уже автоматически установил файлы для сервера-посредника при установке файлов для пула серверов переднего сервера или сервера Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="35ceb-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="35ceb-108">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="35ceb-108">In this section</span></span>

- [<span data-ttu-id="35ceb-109">Необходимые условия для обеспечения безопасности и Корпоративная голосовая связь в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="35ceb-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="35ceb-110">Развертывание сервера-посредника в построителье топологий в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="35ceb-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="35ceb-111">Определение шлюза в построителье топологий в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="35ceb-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="35ceb-112">Определение дополнительных магистральных магистрали в построителье топологий в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="35ceb-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="35ceb-113">Установка файлов для сервера-посредника в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="35ceb-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="35ceb-114">Настройка магистральных магистральных звонков в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="35ceb-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="35ceb-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="35ceb-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="35ceb-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="35ceb-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="35ceb-117">Создание или изменение правила нормализации в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="35ceb-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="35ceb-118">Создание или изменение телефонной плана в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="35ceb-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="35ceb-119">Настройка политик голосовой почты, записей использования PSTN и маршрутов голосовых вызовов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="35ceb-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="35ceb-120">Enable users for Корпоративная голосовая связь in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="35ceb-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="35ceb-121">Развертывание расширенных Корпоративная голосовая связь в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="35ceb-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="35ceb-122">Развертывание функций управления звонками в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="35ceb-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="35ceb-123">См. также</span><span class="sxs-lookup"><span data-stu-id="35ceb-123">See also</span></span>

[<span data-ttu-id="35ceb-124">Планирование Корпоративная голосовая связь в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="35ceb-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

