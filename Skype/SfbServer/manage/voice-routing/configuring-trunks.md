---
title: Настройка магистральных магистральных звонков в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: В рамках Корпоративная голосовая связь вы можете настроить магистраль между сервером-посредником и одним или более одноранговых узлами, чтобы обеспечить подключение к телефонной сети общего перейти к Корпоративная голосовая связь клиентам и устройствам в организации.
ms.openlocfilehash: 57b8635d635c0fd0b8c41c95f92af768ff84dfd4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800119"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a><span data-ttu-id="ee99e-103">Настройка магистральных магистральных звонков в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ee99e-103">Configuring trunks in Skype for Business Server</span></span>

<span data-ttu-id="ee99e-104">В рамках развертывания Корпоративная голосовая связь можно настроить магистраль между сервером-посредником и одним или более из следующих одноранговых серверов, чтобы обеспечить подключение к STN для клиентов Корпоративная голосовая связь и устройств в организации:</span><span class="sxs-lookup"><span data-stu-id="ee99e-104">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>

- <span data-ttu-id="ee99e-105">Подключение магистрали SIP к поставщику услуг Интернет-телефонии</span><span class="sxs-lookup"><span data-stu-id="ee99e-105">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
- <span data-ttu-id="ee99e-106">Шлюз ТСОП</span><span class="sxs-lookup"><span data-stu-id="ee99e-106">PSTN gateway</span></span>
- <span data-ttu-id="ee99e-107">УАТС</span><span class="sxs-lookup"><span data-stu-id="ee99e-107">Private branch exchange (PBX)</span></span>

<span data-ttu-id="ee99e-108">For details, see [Plan for PSTN connectivity in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)</span><span class="sxs-lookup"><span data-stu-id="ee99e-108">For details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee99e-109">Прежде чем приступать к настройке магистрали, убедитесь что создана топология и что сервер-посредник и его одноранговый узел настроены и связаны друг с другом.</span><span class="sxs-lookup"><span data-stu-id="ee99e-109">Before you begin trunk configuration, verify that the topology has been created and that the Mediation Server and its peer have been configured and associated with one another.</span></span> <span data-ttu-id="ee99e-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span><span class="sxs-lookup"><span data-stu-id="ee99e-110">For details, see [Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ee99e-111">В рамках настройки магистрали можно включить функцию обхода сервера-посредника Skype для бизнеса Server, которая позволяет мультимедиа обходить сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="ee99e-111">As a part of trunk configuration, you can enable the Skype for Business Server media bypass feature, which enables media to bypass the Mediation Server.</span></span> <span data-ttu-id="ee99e-112">Магистрали можно настроить как с включенной, так и с выключенной функцией медиа-посредника, но мы настоятельно рекомендуем включить эту функцию.</span><span class="sxs-lookup"><span data-stu-id="ee99e-112">Trunks can be configured either with or without media bypass enabled, but we strongly recommend that you enable it.</span></span> <span data-ttu-id="ee99e-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="ee99e-113">For details, see [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).</span></span>
