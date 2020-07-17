---
title: Создание схемы здания для панели мониторинга качества звонков (CQD)
ms.author: lolaj
author: LolaJacobsen
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
description: Сведения о том, как создать стандартную карту, которую можно использовать для отправки клиентов и построения данных на панели мониторинга качества вызова (CQD).
ms.openlocfilehash: 18e88c2de64d2d63589a3cd2ebddbc9643fe4522
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086098"
---
# <a name="create-a-building-map-for-call-quality-dashboard-cqd"></a><span data-ttu-id="07229-103">Создание схемы здания для панели мониторинга качества звонков (CQD)</span><span class="sxs-lookup"><span data-stu-id="07229-103">Create a building map for Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="07229-104">В развертывании Microsoft Teams или Skype для бизнеса Online все клиенты являются внешними.</span><span class="sxs-lookup"><span data-stu-id="07229-104">In a Microsoft Teams or Skype for Business Online deployment, all clients are external.</span></span> <span data-ttu-id="07229-105">В результате по умолчанию все клиенты выводятся как внешние на панели мониторинга качества звонков (CQD) независимо от того, подключен ли клиент к внутренней корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="07229-105">As a result, by default, all clients are reported as outside in Call Quality Dashboard (CQD), regardless of whether the client is connected on an internal corporate network.</span></span>

<span data-ttu-id="07229-106">При работе с CQD необходимо знать расположение конечной точки и определить, подключено ли оно к сети, которую можно управлять и которыми вы не можете управлять, предполагается, что вы можете только улучшить сетевые сети, которыми вы можете управлять.</span><span class="sxs-lookup"><span data-stu-id="07229-106">When you work with CQD, you need to know the location of an endpoint and whether it was connected to a network you can manage or a network you can't manage, the assumption being that you can only improve networks you can manage.</span></span> <span data-ttu-id="07229-107">Отправив подсеть и создавайте информацию в CQD, вы включите CQD, чтобы определить, была ли конечная точка подключена к внутренней (управляемой) сети или внешней (неуправляемой) сети.</span><span class="sxs-lookup"><span data-stu-id="07229-107">By uploading subnet and building information to CQD, you enable CQD to determine whether the endpoint was connected to an internal (managed) network or to an external (unmanaged) network.</span></span> <span data-ttu-id="07229-108">Вот почему важно создать стандартную карту для вашей организации и [загрузить ее в CQD](CQD-upload-tenant-building-data.md).</span><span class="sxs-lookup"><span data-stu-id="07229-108">That's why it's important to create a building map for your organization and [upload it to CQD](CQD-upload-tenant-building-data.md).</span></span>

## <a name="building-mapping-tools"></a><span data-ttu-id="07229-109">Средства сопоставления в зданиях</span><span class="sxs-lookup"><span data-stu-id="07229-109">Building mapping tools</span></span>

<span data-ttu-id="07229-110">Существует множество способов сопоставления подсетей Организации.</span><span class="sxs-lookup"><span data-stu-id="07229-110">There are many ways to map your organization's subnets.</span></span> <span data-ttu-id="07229-111">Если вам нужна помощь, вы можете использовать модуль PowerShell CQDTools, описанный в этой [записи блога](https://aka.ms/cqdtools).</span><span class="sxs-lookup"><span data-stu-id="07229-111">If you need help, you can use the CQDTools PowerShell Module described in this [blog post](https://aka.ms/cqdtools).</span></span> <span data-ttu-id="07229-112">Эти средства основываются на PowerShell и используют сайты и службы Active Directory (AD) и службы Microsoft DHCP для подготовки к заполнению файла здания.</span><span class="sxs-lookup"><span data-stu-id="07229-112">These tools are based on PowerShell and use Active Directory (AD) Sites and Services and Microsoft DHCP services to help pre-populate your building file.</span></span> <span data-ttu-id="07229-113">Эти средства помогут вам решить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="07229-113">These tools will help with the following tasks:</span></span>

1. <span data-ttu-id="07229-114">Запрашивать сайты и службы Active Directory, а также создавать файлы здания на основе данных, содержащихся в.</span><span class="sxs-lookup"><span data-stu-id="07229-114">Query AD Sites and Services, and create a building file based on the information contained within.</span></span>
1. <span data-ttu-id="07229-115">Запросите сервер или серверы Microsoft, чтобы получить сведения о подсети и автоматически создать файл здания.</span><span class="sxs-lookup"><span data-stu-id="07229-115">Query a Microsoft DHCP server or servers to pull subnet information and automatically create a building file.</span></span>
1. <span data-ttu-id="07229-116">Проверка существующего стандартного файла с поиском повторений и перекрытий.</span><span class="sxs-lookup"><span data-stu-id="07229-116">Validate an existing building file, checking for duplicates and overlaps.</span></span>
1. <span data-ttu-id="07229-117">Поиск несопоставленных подсетей в CQD.</span><span class="sxs-lookup"><span data-stu-id="07229-117">Find unmapped subnets in CQD.</span></span>

## <a name="related-topics"></a><span data-ttu-id="07229-118">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="07229-118">Related topics</span></span>

[<span data-ttu-id="07229-119">Отправка клиента и создание данных в CQD</span><span class="sxs-lookup"><span data-stu-id="07229-119">Upload tenant and building data in CQD</span></span>](CQD-upload-tenant-building-data.md)