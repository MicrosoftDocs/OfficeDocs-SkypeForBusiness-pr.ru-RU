---
title: Создание карты здания для панели мониторинга качества звонка (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Узнайте, как создать карту здания, которую можно использовать для отправки данных о клиенте и здании на панели мониторинга качества звонка (CQD).
ms.openlocfilehash: 890e5e9b394cf8b600e635014c90ebb9053a1e07
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46584038"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="93815-103">Создание карты здания для панели мониторинга качества звонка (CQD)</span><span class="sxs-lookup"><span data-stu-id="93815-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="93815-104">В развертывании Microsoft Teams или Skype для бизнеса Online все клиенты являются внешними.</span><span class="sxs-lookup"><span data-stu-id="93815-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="93815-105">В результате по умолчанию на панели мониторинга качества звонка (CQD) все клиенты сообщаются как внешние независимо от того, подключен ли клиент к внутренней корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="93815-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="93815-106">При работе с CQD необходимо знать расположение конечной точки и то, подключена ли она к сети, которую вы можете управлять, или к сети, которую вы не можете управлять, предполагая, что вы можете улучшить только те сети, которые вы можете управлять.</span><span class="sxs-lookup"><span data-stu-id="93815-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="93815-107">Выкладывая сведения о подсети и здания в CQD, вы включаете CQD, чтобы определить, подключена ли конечная точка к внутренней (управляемой) или внешней (неуправляемой) сети.</span><span class="sxs-lookup"><span data-stu-id="93815-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="93815-108">Поэтому очень важно создать карту здания для организации и добавить ее в [CQD.](CQD-upload-tenant-building-data.md)</span><span class="sxs-lookup"><span data-stu-id="93815-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="93815-109">Средства сопоставления зданий</span><span class="sxs-lookup"><span data-stu-id="93815-109">Building mapping tools</span></span>

<span data-ttu-id="93815-110">Существует множество способов соотоставить подсети организации.</span><span class="sxs-lookup"><span data-stu-id="93815-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="93815-111">Если вам нужна помощь, воспользуйтесь модулем PowerShell CQDTools, описанным в этой [записи блога.](https://aka.ms/cqdtools)</span><span class="sxs-lookup"><span data-stu-id="93815-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="93815-112">Эти средства основаны на PowerShell и используют сайты и службы Active Directory (AD) и службы DHCP Майкрософт для предварительного заполнения файла здания.</span><span class="sxs-lookup"><span data-stu-id="93815-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="93815-113">Эти средства помогут вам в следующих задачах:</span><span class="sxs-lookup"><span data-stu-id="93815-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="93815-114">Запрос сайтов и служб AD и создание файла здания на основе содержащихся в них сведений.</span><span class="sxs-lookup"><span data-stu-id="93815-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="93815-115">Запросите сервер или сервер Microsoft DHCP, чтобы получить сведения о подсети и автоматически создать файл здания.</span><span class="sxs-lookup"><span data-stu-id="93815-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="93815-116">Проверка существующего файла здания, проверка на совпадения и повторы.</span><span class="sxs-lookup"><span data-stu-id="93815-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="93815-117">Поиск неподтверщенных подсетей в CQD.</span><span class="sxs-lookup"><span data-stu-id="93815-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="93815-118">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="93815-118">Related topics</span></span>

[<span data-ttu-id="93815-119">Upload клиента и здания в CQD</span><span class="sxs-lookup"><span data-stu-id="93815-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)