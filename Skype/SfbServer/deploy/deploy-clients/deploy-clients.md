---
title: Развертывание клиентов для Скайп для Business Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Сводка: Обзор методов установки enterprise client для Скайп для бизнеса.'
ms.openlocfilehash: 31d3f6b9fbc611ae434e10bc1208d95a645ba3bd
ms.sourcegitcommit: 47e5f6a0440f646d67bc3ca7c232df9558f78040
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "33641472"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="da9bc-103">Развертывание клиентов для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="da9bc-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="da9bc-104">**Сводка:** Обзор корпоративных клиентов методы Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="da9bc-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="da9bc-105">Как развернуть Скайп для бизнеса для пользователей зависит от того, является ли вы приобрели Скайп для бизнеса в рамках плана Office 365 или приобрести лицензированную версию тома Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="da9bc-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="da9bc-106">**Office 365** Если у вас есть план Office 365, которая включает в себя Скайп для бизнеса, технология установки, которая используется называется Click-to-Run.</span><span class="sxs-lookup"><span data-stu-id="da9bc-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="da9bc-107">В Office 365 можно позволить пользователям установить Скайп для бизнеса на свои компьютеры с портала Office 365.</span><span class="sxs-lookup"><span data-stu-id="da9bc-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="da9bc-108">Или Скайп для бизнеса можно развернуть для пользователей, загрузив программное обеспечение в локальную сеть и затем с помощью существующие средства развертывания программного обеспечения, например, с помощью Microsoft System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="da9bc-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="da9bc-109">Сведения об установке о Скайп для бизнеса с Office 365 см [Скайп для клиента бизнеса в Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="da9bc-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="da9bc-110">**Том с корпоративным лицензированием** При наличии лицензированную версию Скайп для бизнеса 2015 или клиента 2016 многопользовательской установки технология, которая используется — установщика Windows (MSI).</span><span class="sxs-lookup"><span data-stu-id="da9bc-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="da9bc-111">Пакет установки на основе установщика Windows состоит из нескольких файлов MSI.</span><span class="sxs-lookup"><span data-stu-id="da9bc-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="da9bc-112">Не зависящий от языка основной пакет MSI объединен с одним или несколькими языковыми пакетами, что в совокупности и представляет полный продукт.</span><span class="sxs-lookup"><span data-stu-id="da9bc-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="da9bc-113">При настройке отдельные пакеты собираются вместе и выполняются задачи настройки и обслуживания во время и после установки Office на пользовательские компьютеры.</span><span class="sxs-lookup"><span data-stu-id="da9bc-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="da9bc-114">Скайп для клиента Business 2019 использует Click-to-Run программы установки.</span><span class="sxs-lookup"><span data-stu-id="da9bc-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="da9bc-115">В этом разделе описываются способы использования и настройки установщика Windows для развертывания Скайп для клиента Business для пользователей с помощью обычного процедур.</span><span class="sxs-lookup"><span data-stu-id="da9bc-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="da9bc-116">Надстройка собраний Скайп для Microsoft Office, которая поддерживает Управление собраниями в клиенте системы обмена сообщениями и совместной работы Outlook, автоматическая установка вместе с Скайп пользователей.</span><span class="sxs-lookup"><span data-stu-id="da9bc-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="da9bc-117">Программа установки Office 365 не приводит к удалению предыдущих версий Lync.</span><span class="sxs-lookup"><span data-stu-id="da9bc-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="da9bc-118">Скайп для клиента Business устанавливает рядом с другими клиентами Lync.</span><span class="sxs-lookup"><span data-stu-id="da9bc-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="da9bc-119">Установка клиентов Windows</span><span class="sxs-lookup"><span data-stu-id="da9bc-119">Installing Windows clients</span></span>

- [<span data-ttu-id="da9bc-120">Настройка установки клиента Windows в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="da9bc-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="da9bc-121">Настройка взаимодействия с клиентом в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="da9bc-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="da9bc-122">Настройка интеллектуального списка контактов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="da9bc-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="da9bc-123">Установка устройства клиентов</span><span class="sxs-lookup"><span data-stu-id="da9bc-123">Installing device clients</span></span>

- [<span data-ttu-id="da9bc-124">Install and test Skype for Business for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="da9bc-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="da9bc-125">Install and test Skype for Business for iOS</span><span class="sxs-lookup"><span data-stu-id="da9bc-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="da9bc-126">Развертывание подключаемого модуля VDI Lync с Скайп for Business Server</span><span class="sxs-lookup"><span data-stu-id="da9bc-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="da9bc-127">Развертывание веб-загрузки клиентов в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="da9bc-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="da9bc-128">Настройка клиента на Mac в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="da9bc-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="da9bc-129">См. также</span><span class="sxs-lookup"><span data-stu-id="da9bc-129">See also</span></span>

[<span data-ttu-id="da9bc-130">Развертывание Скайп для клиента бизнеса в Office 365</span><span class="sxs-lookup"><span data-stu-id="da9bc-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)