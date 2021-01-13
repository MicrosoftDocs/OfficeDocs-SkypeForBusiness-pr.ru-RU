---
title: Развертывание клиентов для Skype для бизнеса Server
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: Сводка. Обзор методов установки корпоративных клиентов для Skype для бизнеса.
ms.openlocfilehash: ccaed5620c7f524a5a39fc6a35e6d688cd97a0eb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805699"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="636ce-103">Развертывание клиентов для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="636ce-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="636ce-104">**Сводка:** Обзор методов установки корпоративных клиентов для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="636ce-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="636ce-105">Развертывание Skype для бизнеса для пользователей зависит от того, приобрели ли вы Skype для бизнеса в рамках плана Microsoft 365 или Office 365 или приобрели версию Skype для бизнеса с много лицензиями.</span><span class="sxs-lookup"><span data-stu-id="636ce-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of a Microsoft 365 or Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="636ce-106">**Microsoft 365 или Office 365** Если у вас есть план Microsoft 365 или Office 365, который включает Skype для бизнеса, используемая технология установки называется технологией "нажми и запускай".</span><span class="sxs-lookup"><span data-stu-id="636ce-106">**Microsoft 365 or Office 365** If you have a Microsoft 365 or Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="636ce-107">Вы можете позволить пользователям самостоятельно устанавливать Skype для бизнеса из Центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="636ce-107">You can let your users install Skype for Business for themselves from the Microsoft 365 admin center.</span></span> <span data-ttu-id="636ce-108">Кроме того, вы можете развернуть Skype для бизнеса для пользователей, скачав программное обеспечение в локализованную сеть, а затем используя существующие средства развертывания программного обеспечения, например Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="636ce-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="636ce-109">Сведения об установке Skype для бизнеса, которая поставляется вместе с Microsoft 365 и Office 365, см. в сведениях о развертывании клиента Skype для бизнеса в [Microsoft 365 или Office 365.](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)</span><span class="sxs-lookup"><span data-stu-id="636ce-109">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="636ce-110">**Volume licensed** Если у вас есть клиент Skype для бизнеса 2015 или 2016 с много лицензией, используемая технология установки — установщик Windows (MSI).</span><span class="sxs-lookup"><span data-stu-id="636ce-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="636ce-111">Пакет установки на основе установщика Windows состоит из нескольких MSI-файлов.</span><span class="sxs-lookup"><span data-stu-id="636ce-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="636ce-112">Не зависящий от языка основной пакет MSI объединен с одним или несколькими языковыми пакетами, что в совокупности и представляет полный продукт.</span><span class="sxs-lookup"><span data-stu-id="636ce-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="636ce-113">При настройке отдельные пакеты собираются вместе и выполняются задачи настройки и обслуживания во время и после установки Office на пользовательские компьютеры.</span><span class="sxs-lookup"><span data-stu-id="636ce-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="636ce-114">Клиент Skype для бизнеса 2019 использует установщики "нажми и выйми".</span><span class="sxs-lookup"><span data-stu-id="636ce-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="636ce-115">В темах этого раздела описывается использование и настройка установщика Windows для развертывания клиента Skype для бизнеса для пользователей с помощью обычных процедур.</span><span class="sxs-lookup"><span data-stu-id="636ce-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="636ce-116">Надстройка для собраний Skype для Microsoft Office, которая поддерживает управление собраниями в клиенте outlook для обмена сообщениями и совместной работы, устанавливается автоматически с клиентами Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="636ce-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="636ce-117">Программы установки Microsoft 365 и Office 365 не будут удалить предыдущие версии Lync.</span><span class="sxs-lookup"><span data-stu-id="636ce-117">The Microsoft 365 and Office 365 setup programs don't uninstall previous versions of Lync.</span></span> <span data-ttu-id="636ce-118">Клиент Skype для бизнеса устанавливается вместе с другими клиентами Lync.</span><span class="sxs-lookup"><span data-stu-id="636ce-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="636ce-119">Установка клиентов Windows</span><span class="sxs-lookup"><span data-stu-id="636ce-119">Installing Windows clients</span></span>

- [<span data-ttu-id="636ce-120">Настройка установки клиента Windows в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="636ce-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="636ce-121">Настройка работы с клиентом в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="636ce-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="636ce-122">Настройка интеллектуального списка контактов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="636ce-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="636ce-123">Установка клиентов устройств</span><span class="sxs-lookup"><span data-stu-id="636ce-123">Installing device clients</span></span>

- [<span data-ttu-id="636ce-124">Установка и тестирование Skype для бизнеса для Windows Phone</span><span class="sxs-lookup"><span data-stu-id="636ce-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="636ce-125">Установка и тестирование Skype для бизнеса для iOS</span><span class="sxs-lookup"><span data-stu-id="636ce-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="636ce-126">Развертывание подключаемого модуль Lync VDI со Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="636ce-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="636ce-127">Развертывание загружаемых веб-клиентов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="636ce-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="636ce-128">Настройка клиентского опыта Mac в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="636ce-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="636ce-129">См. также</span><span class="sxs-lookup"><span data-stu-id="636ce-129">See also</span></span>

[<span data-ttu-id="636ce-130">Развертывание клиента Skype для бизнеса в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="636ce-130">Deploy the Skype for Business client in Microsoft 365 or Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
