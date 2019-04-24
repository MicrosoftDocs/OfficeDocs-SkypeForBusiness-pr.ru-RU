---
title: Настройка установки клиента Windows в Скайп для Business Server
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Сводка: Общие сведения о способы установки и средства для Скайп для бизнеса.'
ms.openlocfilehash: d6458c1ec81ea67162a53107582249f301102ebd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212714"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="d2ea3-103">Настройка установки клиента Windows в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="d2ea3-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="d2ea3-104">**Сводка:** Общие сведения о способы установки и средства для Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d2ea3-105">Сведения об установке о Скайп для бизнеса с Office 365 см [Скайп для клиента бизнеса в Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="d2ea3-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="d2ea3-106">Администраторы предприятия можно настроить установку на основе установщика Windows (MSI-) корпоративных версиях Скайп для бизнеса с помощью методы, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="d2ea3-107">Так как не единый инструмент предоставляет все параметры настройки, скорее всего используется сочетание этих методов в вашей Скайп по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="d2ea3-108">При развертывании могут пригодиться средства, перечисленные в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="d2ea3-109">[Использование центра развертывания Office (OCT) в Скайп для Business Server](use-the-office-customization-tool-oct.md) для настройки параметров установки и функции для Скайп для бизнеса и других программ Office.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="d2ea3-110">[Использование файла Config.xml для выполнения задач установки в Скайп для Business Server](use-config-xml-to-perform-installation-tasks.md) , чтобы указать путь к точке сетевой установки и выполнения автоматической установки.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="d2ea3-111">[Используйте параметры командной строки в Скайп для Business Server](use-setup-command-line-options.md) для указания файла Config.xml для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="d2ea3-112">[Настройка политики начальной загрузки клиентов в Скайп для Business Server](configure-client-bootstrapping-policies.md) с помощью оснастки консоли MMC редактора объектов групповой политики.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="d2ea3-113">Возможно, другие параметры, необходимые для настройки при развертывании продуктов Office.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="d2ea3-114">Разделы в этом разделе приводится обзор эти средства настройки и обсудить замечания Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="d2ea3-115">Здесь предоставляются ссылки на подробную справку Office по каждому средству.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-115">Included are links to detailed Office help for each tool.</span></span> 
  

