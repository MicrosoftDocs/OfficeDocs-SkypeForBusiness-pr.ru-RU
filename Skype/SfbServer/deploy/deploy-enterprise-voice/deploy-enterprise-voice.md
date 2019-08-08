---
title: Развертывание корпоративной голосовой связи в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Сводка: сведения о том, как развернуть корпоративный голосовую почту для сервера Skype для бизнеса на центральном сайте.'
ms.openlocfilehash: 3e85ac96415788e8e15ba1ed11786864b6fc3124
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245429"
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="b1482-103">Развертывание корпоративной голосовой связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1482-103">Deploy Enterprise Voice in Skype for Business Server</span></span>

<span data-ttu-id="b1482-104">**Сводка:** Сведения о том, как развернуть корпоративную голосовую почту для Skype для бизнеса Server на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="b1482-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server at a central site.</span></span>

<span data-ttu-id="b1482-105">Этот раздел используется для развертывания корпоративной голосовой связи на центральном веб-сайте.</span><span class="sxs-lookup"><span data-stu-id="b1482-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="b1482-106">Чтобы развернуть корпоративную голосовую почту на сайте филиала, перейдите к разделу [Развертывание сайтов филиалов](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span><span class="sxs-lookup"><span data-stu-id="b1482-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](https://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>

<span data-ttu-id="b1482-107">Этот раздел содержит процедуры для развертываний, в которых сервер-посредник размещен на каждом сервере переднего плана или стандартном сервере выпуска Standard, как рекомендуется, а также для развертываний с помощью пула серверов с изолированными исправлениями. Вы можете пропустить следующее содержимое, если вы используете Topology Builder, чтобы определить и опубликовать топологию, которая будет высвоена серверу-посреднику на каждом сервере переднего плана или стандартном сервере выпуска Standard Edition, так как мастер развертывания уже автоматически установил файлы для Сервер для устранения проблем при установке файлов для пула серверов переднего плана или стандартного выпуска сервера:</span><span class="sxs-lookup"><span data-stu-id="b1482-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="b1482-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="b1482-108">In this section</span></span>

- [<span data-ttu-id="b1482-109">Требования к безопасности и конфигурации для корпоративной голосовой связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1482-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server</span></span>](enterprise-voice-security.md)

- [<span data-ttu-id="b1482-110">Развертывание сервера-посредника в построителе топологии в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1482-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server</span></span>](deploy-a-mediation-server.md)

- [<span data-ttu-id="b1482-111">Определение шлюза в построителе топологии в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1482-111">Define a gateway in Topology Builder in Skype for Business Server</span></span>](define-a-gateway.md)

- [<span data-ttu-id="b1482-112">Определение дополнительных каналов в построителе топологии в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1482-112">Define additional trunks in Topology Builder in Skype for Business Server</span></span>](define-additional-trunks.md)

- [<span data-ttu-id="b1482-113">Установка сервера исправлений в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1482-113">Install the files for Mediation Server in Skype for Business Server</span></span>](install-mediation-server.md)

- [<span data-ttu-id="b1482-114">Настройка каналов связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1482-114">Configure trunks in Skype for Business Server</span></span>](configure-trunks.md)

- [<span data-ttu-id="b1482-115">Создание или изменение правила трансляции для презентации идентификации вызывающего абонента в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1482-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>](caller-id-presentation-rules.md)

- [<span data-ttu-id="b1482-116">Создание или изменение правила трансляции для вызываемого удостоверения презентация в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1482-116">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>](called-id-presentation-rules.md)

- [<span data-ttu-id="b1482-117">Создание и изменение правила нормализации в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b1482-117">Create or modify a normalization rule in Skype for Business</span></span>](normalization-rules.md)

- [<span data-ttu-id="b1482-118">Создание и изменение абонентской группы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1482-118">Create or modify a dial plan in Skype for Business Server</span></span>](dial-plans.md)

- [<span data-ttu-id="b1482-119">Настройка политик голосовой связи, записей использования PSTN и голосовых маршрутов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b1482-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>](voice-and-pstn.md)

- [<span data-ttu-id="b1482-120">Включение пользователей корпоративной голосовой связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1482-120">Enable users for Enterprise Voice in Skype for Business Server</span></span>](enable-users-for-enterprise-voice.md)

- [<span data-ttu-id="b1482-121">Развертывание улучшенных функций голосовой связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1482-121">Deploy advanced Enterprise Voice features in Skype for Business Server</span></span>](deploy-advanced-enterprise-voice-features.md)

- [<span data-ttu-id="b1482-122">Развертывание функций управления звонками в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b1482-122">Deploy call management features in Skype for Business</span></span>](deploy-call-management-features.md)

## <a name="see-also"></a><span data-ttu-id="b1482-123">См. также</span><span class="sxs-lookup"><span data-stu-id="b1482-123">See also</span></span>

[<span data-ttu-id="b1482-124">Планирование корпоративной голосовой связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1482-124">Plan for Enterprise Voice in Skype for Business Server</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

