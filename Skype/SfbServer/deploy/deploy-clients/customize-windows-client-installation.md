---
title: Настройка установки клиента Windows в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Сводка: Общие сведения о способах установки и средствах для Skype для бизнеса.'
ms.openlocfilehash: 40e5b9145f06038e76aee0b77b287e6dce9a8b3b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288580"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="d7c30-103">Настройка установки клиента Windows в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d7c30-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="d7c30-104">**Сводка:** Общие сведения о способах установки и средствах для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d7c30-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d7c30-105">Сведения об установке Skype для бизнеса, которые поставляются вместе с Office 365, можно найти [в разделе Развертывание клиента Skype для бизнеса в office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="d7c30-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="d7c30-106">Корпоративные администраторы могут настроить установленную на основе установщика Windows (MSI) версию Skype для бизнеса с помощью описанных ниже способов.</span><span class="sxs-lookup"><span data-stu-id="d7c30-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="d7c30-107">Так как ни один из средств не предоставляет никаких вариантов настройки, скорее всего, вы будете использовать сочетание этих способов в развертывании Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d7c30-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="d7c30-108">При развертывании могут пригодиться средства, перечисленные в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="d7c30-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="d7c30-109">С [помощью средства развертывания Office (OCT) в Skype для бизнеса Server](use-the-office-customization-tool-oct.md) можно настраивать параметры и функции Skype для бизнеса и других программ Office.</span><span class="sxs-lookup"><span data-stu-id="d7c30-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="d7c30-110">[С помощью файла config. XML вы можете выполнять задачи по установке в Skype для бизнеса Server](use-config-xml-to-perform-installation-tasks.md) , чтобы указать путь к точке сетевой установки и выполнить автоматическую установку.</span><span class="sxs-lookup"><span data-stu-id="d7c30-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="d7c30-111">С [помощью параметров командной строки программы установки в Skype для бизнеса Server](use-setup-command-line-options.md) укажите файл config. XML для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="d7c30-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="d7c30-112">[Настройка политик начальной настройки клиента в Skype для бизнеса Server](configure-client-bootstrapping-policies.md) с помощью оснастки MMC "Редактор объектов групповой политики".</span><span class="sxs-lookup"><span data-stu-id="d7c30-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="d7c30-113">Возможно, вы захотите настроить другие параметры при развертывании набора продуктов Office.</span><span class="sxs-lookup"><span data-stu-id="d7c30-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="d7c30-114">В этом разделе представлены общие сведения о средствах настройки и обсуждаются вопросы, касающиеся Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d7c30-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="d7c30-115">Здесь предоставляются ссылки на подробную справку Office по каждому средству.</span><span class="sxs-lookup"><span data-stu-id="d7c30-115">Included are links to detailed Office help for each tool.</span></span> 
  

