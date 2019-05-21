---
title: Развертывание сервера видеосвязи в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 'Сводка: развертывание роли сервера ВИС в Skype для бизнеса Server.'
ms.openlocfilehash: c6ee0e52a4ac84622fee9ba281a64d1094c38c4c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302737"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="18424-103">Развертывание сервера видеосвязи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="18424-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="18424-104">**Сводка:** Развертывание роли сервера ВИС в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="18424-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="18424-105">Skype для бизнеса Server теперь может интегрироваться непосредственно с системами для проведения телеконференций Cisco (Вткс), например с компанией Cisco C60 или Cisco MX300.</span><span class="sxs-lookup"><span data-stu-id="18424-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="18424-106">Для этого требуется введение в новую роль сервера видеосвязи (ВИС) и правильную конфигурацию обоих ВИС и оборудования, с которым оно будет взаимодействовать.</span><span class="sxs-lookup"><span data-stu-id="18424-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="18424-107">VTC проходит регистрацию в существующей инфраструктуре Cisco, например Cisco Unified Communication Manager (CUCM), а между CUCM и пулом VIS используется видеомагистраль SIP.</span><span class="sxs-lookup"><span data-stu-id="18424-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="18424-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="18424-108">In this section</span></span>

<span data-ttu-id="18424-109">Настройка взаимодействия между серверов видеовзаимодействия или пулом и системами VTC требуется выполнения следующих пяти процедур:</span><span class="sxs-lookup"><span data-stu-id="18424-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="18424-110">Создание пула ВИС в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="18424-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="18424-111">Развертывание роли сервера ВИС в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="18424-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="18424-112">Настройка сервера видеосвязи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="18424-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="18424-113">Настройка КУКМ для взаимодействия с Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="18424-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="18424-114">Настройка ВТК для взаимодействия с Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="18424-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="18424-115">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="18424-115">Related sections</span></span>

[<span data-ttu-id="18424-116">Планирование сервера видеосвязи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="18424-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

