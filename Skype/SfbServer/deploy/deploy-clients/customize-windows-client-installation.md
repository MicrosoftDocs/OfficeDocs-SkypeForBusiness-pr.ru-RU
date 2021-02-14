---
title: Настройка установки клиента Windows в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: Сводка. Обзор методов установки и средств для Skype для бизнеса.
ms.openlocfilehash: 001224369e46978e96ee063b31fcb546ef213a05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805719"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="e7639-103">Настройка установки клиента Windows в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e7639-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="e7639-104">**Сводка:** Обзор методов установки и средств для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e7639-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7639-105">Сведения об установке Skype для бизнеса, которая поставляется вместе с Microsoft 365 и Office 365, см. в сведениях о развертывании клиента Skype для бизнеса в [Microsoft 365 или Office 365.](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)</span><span class="sxs-lookup"><span data-stu-id="e7639-105">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="e7639-106">Администраторы предприятия могут настраивать установку версий Skype для бизнеса с корпоративной лицензией на основе установщика Windows (MSI), используя методы, рассмотренные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e7639-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="e7639-107">Так как ни одно средство не предоставляет все параметры настройки, скорее всего, вы будете использовать сочетание этих методов в развертывании Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e7639-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="e7639-108">Можно использовать средства, описанные в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="e7639-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="e7639-109">[Используйте средство настройки Office (OCT) в Skype для](use-the-office-customization-tool-oct.md) бизнеса Server для настройки параметров установки и компонентов Skype для бизнеса и других программ Office.</span><span class="sxs-lookup"><span data-stu-id="e7639-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="e7639-110">[Используйте Config.xml для выполнения](use-config-xml-to-perform-installation-tasks.md) задач установки в Skype для бизнеса Server, чтобы указать путь к точке сетевой установки и выполнить установку в тихом режиме.</span><span class="sxs-lookup"><span data-stu-id="e7639-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="e7639-111">[Используйте параметры командной строки](use-setup-command-line-options.md) программы установки в Skype для бизнеса Server, чтобы указать Config.xml для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="e7639-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="e7639-112">[Настройте политики загрузки](configure-client-bootstrapping-policies.md) клиентов в Skype для бизнеса Server с помощью оснастки редактора объектов групповой политики MMC.</span><span class="sxs-lookup"><span data-stu-id="e7639-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="e7639-113">Скорее всего, при развертывании набора продуктов Office вы захотите настроить другие параметры.</span><span class="sxs-lookup"><span data-stu-id="e7639-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="e7639-114">В темах этого раздела приводится обзор этих средств настройки и рассматриваются вопросы, связанные со Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e7639-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="e7639-115">Здесь предоставляются ссылки на подробную справку Office по каждому средству.</span><span class="sxs-lookup"><span data-stu-id="e7639-115">Included are links to detailed Office help for each tool.</span></span> 
  

