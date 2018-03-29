---
title: Развертывание корпоративной голосовой связи в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/1/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
description: 'Сводка: Узнайте, как развертывание корпоративной голосовой связи для Скайп для 2015 Business Server в центральном узле.'
ms.openlocfilehash: d7c6dc347991c198d445932463a44d9fe1a4ff89
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-enterprise-voice-in-skype-for-business-server-2015"></a><span data-ttu-id="97d6b-103">Развертывание корпоративной голосовой связи в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="97d6b-103">Deploy Enterprise Voice in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="97d6b-104">**Сводка:** Сведения о развертывании корпоративной голосовой связи для Скайп для 2015 Business Server в центральном узле.</span><span class="sxs-lookup"><span data-stu-id="97d6b-104">**Summary:** Learn how to deploy Enterprise Voice for Skype for Business Server 2015 at a central site.</span></span>
  
<span data-ttu-id="97d6b-105">Используйте этот раздел для развертывания корпоративной голосовой связи в центральном узле.</span><span class="sxs-lookup"><span data-stu-id="97d6b-105">Use this topic to deploy Enterprise Voice at a central site.</span></span> <span data-ttu-id="97d6b-106">Развертывание корпоративной голосовой связи в филиале, перейдите к [Развертывание сайтов филиалов](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span><span class="sxs-lookup"><span data-stu-id="97d6b-106">To deploy Enterprise Voice at a branch site, skip to [Deploying Branch Sites](http://technet.microsoft.com/library/1475dee0-66ae-4ee5-b6f1-7409b4bbff45.aspx).</span></span>
  
<span data-ttu-id="97d6b-107">В этом разделе приведены действия для развертываний, в котором сервер-посредник совмещен на каждом сервере переднего плана или сервере Standard Edition, соответствии с рекомендациями, а также для развертываний с автономного пула серверов-посредников. Следующие материалы можно пропустить, если Topology Builder используется для определения и публикации топологии, collocates сервера-посредника на каждом сервере переднего плана или сервере Standard Edition, так как мастер развертывания уже автоматически устанавливается в файлы Сервер-посредник при установке файлов для пула серверов переднего плана или сервера Standard Edition:</span><span class="sxs-lookup"><span data-stu-id="97d6b-107">This section includes procedures for deployments in which a Mediation Server is collocated on each Front End Server or Standard Edition server, as recommended, and also for deployments with a stand-alone Mediation Server pool.You can skip the following content if you used Topology Builder to define and publish a topology that collocates a Mediation Server on each Front End Server or Standard Edition server, because Deployment Wizard already automatically installed the files for Mediation Server when you installed files for your Front End Server pool or Standard Edition server:</span></span>
## <a name="in-this-section"></a><span data-ttu-id="97d6b-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="97d6b-108">In this section</span></span>

- [<span data-ttu-id="97d6b-109">Предварительные требования безопасности и конфигурации для корпоративной голосовой связи в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="97d6b-109">Security and configuration prerequisites for Enterprise Voice in Skype for Business Server 2015</span></span>](enterprise-voice-security.md)
    
- [<span data-ttu-id="97d6b-110">Развертывание сервера-посредника в построителе топологий в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="97d6b-110">Deploy a Mediation Server in Topology Builder in Skype for Business Server 2015</span></span>](deploy-a-mediation-server.md)
    
- [<span data-ttu-id="97d6b-111">Определение шлюза в построителе топологий в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="97d6b-111">Define a gateway in Topology Builder in Skype for Business Server 2015</span></span>](define-a-gateway.md)
    
- [<span data-ttu-id="97d6b-112">Определение дополнительных магистралей в построителе топологий в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="97d6b-112">Define additional trunks in Topology Builder in Skype for Business Server 2015</span></span>](define-additional-trunks.md)
    
- [<span data-ttu-id="97d6b-113">Для установки сервера-посредника в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="97d6b-113">Install the files for Mediation Server in Skype for Business Server 2015</span></span>](install-mediation-server.md)
    
- [<span data-ttu-id="97d6b-114">Настройка магистрали в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="97d6b-114">Configure trunks in Skype for Business Server 2015</span></span>](configure-trunks.md)
    
- [<span data-ttu-id="97d6b-115">Создание или изменение правила преобразования для идентификатора звонящего в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="97d6b-115">Create or modify a translation rule for caller ID presentation in Skype for Business Server 2015</span></span>](caller-id-presentation-rules.md)
    
- [<span data-ttu-id="97d6b-116">Создание или изменение правила преобразования для называемое идентификатор представления в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="97d6b-116">Create or modify a translation rule for called ID presentation in Skype for Business Server 2015</span></span>](called-id-presentation-rules.md)
    
- [<span data-ttu-id="97d6b-117">Создание или изменение правила нормализации в Скайп для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="97d6b-117">Create or modify a normalization rule in Skype for Business 2015</span></span>](normalization-rules.md)
    
- [<span data-ttu-id="97d6b-118">Создание или изменение абонентской группы в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="97d6b-118">Create or modify a dial plan in Skype for Business Server 2015</span></span>](dial-plans.md)
    
- [<span data-ttu-id="97d6b-119">Настройка политик голосовой связи, записей использования ТСОП и маршрутов голосовых вызовов в Скайп для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="97d6b-119">Configure voice policies, PSTN usage records, and voice routes in Skype for Business 2015</span></span>](voice-and-pstn.md)
    
- [<span data-ttu-id="97d6b-120">Включение пользователей для корпоративной голосовой связи в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="97d6b-120">Enable users for Enterprise Voice in Skype for Business Server 2015</span></span>](enable-users-for-enterprise-voice.md)
    
- [<span data-ttu-id="97d6b-121">Развертывание расширенных функций корпоративной голосовой связи в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="97d6b-121">Deploy advanced Enterprise Voice features in Skype for Business Server 2015</span></span>](deploy-advanced-enterprise-voice-features.md)
    
- [<span data-ttu-id="97d6b-122">Развертывание функций управления вызовами в Скайп для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="97d6b-122">Deploy call management features in Skype for Business 2015</span></span>](deploy-call-management-features.md)
    
## <a name="see-also"></a><span data-ttu-id="97d6b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="97d6b-123">See also</span></span>

#### 

[<span data-ttu-id="97d6b-124">Планирование корпоративной голосовой связи в Скайп Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="97d6b-124">Plan for Enterprise Voice in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)

