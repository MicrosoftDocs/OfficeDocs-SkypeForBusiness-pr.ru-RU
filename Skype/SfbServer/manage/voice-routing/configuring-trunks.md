---
title: Конфигурация магистралей в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В процессе развертывания корпоративной голосовой связи можно настроить линии связи между сервером-посредником и один или несколько одноранговых узлов для предоставления телефонной сети (общего пользования PSTN) для корпоративной голосовой связи клиентов и устройств в вашей организации.
ms.openlocfilehash: 5e07f0152aac32c4d57962cf619e56777221c955
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883972"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="f4ef8-103">Конфигурация магистралей в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="f4ef8-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="f4ef8-104">В процессе развертывания корпоративной голосовой связи можно настроить линии связи между сервером-посредником и один или несколько следующих партнеров для предоставления телефонной сети (общего пользования PSTN) для корпоративной голосовой связи клиентов и устройств в вашей организации:</span><span class="sxs-lookup"><span data-stu-id="f4ef8-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="f4ef8-105">Подключение магистрали SIP к поставщику услуг Интернет-телефонии</span><span class="sxs-lookup"><span data-stu-id="f4ef8-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="f4ef8-106">Шлюз ТСОП</span><span class="sxs-lookup"><span data-stu-id="f4ef8-106">PSTN gateway</span></span>
- <span data-ttu-id="f4ef8-107">УАТС</span><span class="sxs-lookup"><span data-stu-id="f4ef8-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="f4ef8-108">Дополнительные сведения см [Планирование подключения к ТСОП в Скайп для Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="f4ef8-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4ef8-109">Перед началом настройки магистрали, убедитесь, что топология была создана и, что сервер-посредник и его peer были настроены и связанных друг с другом.</span><span class="sxs-lookup"><span data-stu-id="f4ef8-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="f4ef8-110">Дополнительные сведения см [Определение шлюза в построителе топологий в Скайп для Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="f4ef8-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f4ef8-111">Как часть конфигурации магистрали можно включить Скайп для компонента обхода сервера-посредника Business Server мультимедиа, которое позволяет мультимедиа для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="f4ef8-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="f4ef8-112">Магистральных линий связи можно настроить с помощью или без поддержкой сервера-посредника, но мы настоятельно рекомендуем разрешить его.</span><span class="sxs-lookup"><span data-stu-id="f4ef8-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="f4ef8-113">Для получения дополнительных сведений ознакомьтесь со статьей [Plan для мультимедиа обходить в Скайп для бизнеса](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="f4ef8-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
