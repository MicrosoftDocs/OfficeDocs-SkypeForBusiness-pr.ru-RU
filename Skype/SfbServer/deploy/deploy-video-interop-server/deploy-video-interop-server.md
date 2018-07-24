---
title: Развертывание видео взаимодействия сервера в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: 'Сводка: Deploy VIS серверной роли в Скайп for Business Server.'
ms.openlocfilehash: 8bb21d667774b50fd7a7caddabfbd02e8125a4a2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967574"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="197dc-103">Развертывание видео взаимодействия сервера в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="197dc-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="197dc-104">**Сводка:** Развертывание VIS серверной роли в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="197dc-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="197dc-105">Скайп для Business Server теперь можно интегрировать непосредственно с системами телеконференций Cisco (VTCs), например Cisco C60 или Cisco MX300.</span><span class="sxs-lookup"><span data-stu-id="197dc-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="197dc-106">Для этого необходимо введение новую роль сервера видео взаимодействия сервера по ДИАГОНАЛИ и правильную настройку VIS и оборудование будет будет взаимодействовать с.</span><span class="sxs-lookup"><span data-stu-id="197dc-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="197dc-107">VTC проходит регистрацию в существующей инфраструктуре Cisco, например Cisco Unified Communication Manager (CUCM), а между CUCM и пулом VIS используется видеомагистраль SIP.</span><span class="sxs-lookup"><span data-stu-id="197dc-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="197dc-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="197dc-108">In this section</span></span>

<span data-ttu-id="197dc-109">Настройка взаимодействия между серверов видеовзаимодействия или пулом и системами VTC требуется выполнения следующих пяти процедур:</span><span class="sxs-lookup"><span data-stu-id="197dc-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="197dc-110">Создание пула VIS в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="197dc-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="197dc-111">Развертывание VIS серверной роли в Скайп for Business Server</span><span class="sxs-lookup"><span data-stu-id="197dc-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="197dc-112">Настройка видео взаимодействия сервера в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="197dc-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="197dc-113">Настройка CUCM для взаимодействия с Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="197dc-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="197dc-114">Настройка VTC для взаимодействия с Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="197dc-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="197dc-115">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="197dc-115">Related sections</span></span>

[<span data-ttu-id="197dc-116">Планирование для видео взаимодействия сервера в Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="197dc-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

