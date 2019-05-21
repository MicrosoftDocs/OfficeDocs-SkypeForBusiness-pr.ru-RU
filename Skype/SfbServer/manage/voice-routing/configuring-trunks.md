---
title: Настройка каналов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В рамках развертывания Enterprise Voice вы можете настроить магистраль между сервером-посредником и одним или несколькими узлами для предоставления доступа к общественной коммутируемой телефонной сети (PSTN) для мобильных клиентов и устройств в Организации.
ms.openlocfilehash: c350723720dccee069a28a4d9aa2c40517f6d1bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275005"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="83e33-103">Настройка каналов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="83e33-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="83e33-104">В рамках развертывания Enterprise Voice вы можете настроить магистраль между сервером-посредником и одним или несколькими из указанных ниже одноранговых сетей для предоставления подключения по коммутируемой телефонной сети (PSTN) для корпоративных клиентов и мобильных устройств в Организации.</span><span class="sxs-lookup"><span data-stu-id="83e33-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="83e33-105">Подключение магистрали SIP к поставщику услуг Интернет-телефонии</span><span class="sxs-lookup"><span data-stu-id="83e33-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="83e33-106">Шлюз ТСОП</span><span class="sxs-lookup"><span data-stu-id="83e33-106">PSTN gateway</span></span>
- <span data-ttu-id="83e33-107">УАТС</span><span class="sxs-lookup"><span data-stu-id="83e33-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="83e33-108">Подробнее смотрите в разделе [Планирование подключений PSTN в Skype для бизнеса Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="83e33-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="83e33-109">Перед началом настройки магистрали убедитесь в том, что топология создана и что сервер исправлений и его одноранговые элементы настроены и связаны друг с другом.</span><span class="sxs-lookup"><span data-stu-id="83e33-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="83e33-110">Подробности можно найти [в разделе определение шлюза в построителе топологии в Skype для бизнеса Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="83e33-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="83e33-111">В рамках настройки магистральной конфигурации вы можете включить функцию пропуска мультимедиа в Skype для бизнеса Server, которая позволяет мультимедиа обходить сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="83e33-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="83e33-112">Магистральные магистрали можно настраивать с включенным параметром "обойти" или без него, но настоятельно рекомендуем включить его.</span><span class="sxs-lookup"><span data-stu-id="83e33-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="83e33-113">Подробности можно найти [в разделе Планирование обхода мультимедиа в Skype для бизнеса](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="83e33-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
