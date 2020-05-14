---
title: Настройка установки клиента Windows в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Сводка: обзор способов установки и средств для Skype для бизнеса.'
ms.openlocfilehash: ea8a07bf6a6e00eee93f2a0a8b3ffc756b239ce9
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220839"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="c403d-103">Настройка установки клиента Windows в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c403d-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="c403d-104">**Сводка:** Общие сведения о методах и средствах установки Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c403d-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c403d-105">Сведения об установке Skype для бизнеса, поставляемые с Microsoft 365 и Office 365, приведены [в статье Развертывание клиента Skype для бизнеса в microsoft 365 или office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="c403d-105">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="c403d-106">Администраторы предприятия могут настроить установку на основе установщика Windows (MSI) версии Skype для бизнеса с корпоративной лицензией с помощью методов, описанных в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c403d-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="c403d-107">Так как ни одно средство не предоставляет все параметры настройки, скорее всего, вы будете использовать сочетание этих методов в развертывании Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c403d-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="c403d-108">Вы можете использовать средства, описанные в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="c403d-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="c403d-109">С [помощью центра развертывания Office (OCT) в Skype для бизнеса Server](use-the-office-customization-tool-oct.md) можно настроить параметры установки и функции Skype для бизнеса и других программ Office.</span><span class="sxs-lookup"><span data-stu-id="c403d-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="c403d-110">[Используйте файл config. XML для выполнения задач установки в Skype для бизнеса Server](use-config-xml-to-perform-installation-tasks.md) , чтобы указать путь к точке сетевой установки и выполнить автоматическую установку.</span><span class="sxs-lookup"><span data-stu-id="c403d-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="c403d-111">[Используйте параметры командной строки программы установки в Skype для бизнеса Server](use-setup-command-line-options.md) , чтобы указать файл config. XML для использования во время установки.</span><span class="sxs-lookup"><span data-stu-id="c403d-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="c403d-112">[Настройте политики начальной загрузки клиентов в Skype для бизнеса Server](configure-client-bootstrapping-policies.md) с помощью оснастки MMC редактора объектов групповой политики.</span><span class="sxs-lookup"><span data-stu-id="c403d-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="c403d-113">Скорее всего, будут доступны другие варианты, которые необходимо настроить при развертывании набора продуктов Office.</span><span class="sxs-lookup"><span data-stu-id="c403d-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="c403d-114">В подразделах этого раздела приводится обзор этих средств настройки и рассматриваются вопросы, связанные с Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c403d-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="c403d-115">Здесь предоставляются ссылки на подробную справку Office по каждому средству.</span><span class="sxs-lookup"><span data-stu-id="c403d-115">Included are links to detailed Office help for each tool.</span></span> 
  

