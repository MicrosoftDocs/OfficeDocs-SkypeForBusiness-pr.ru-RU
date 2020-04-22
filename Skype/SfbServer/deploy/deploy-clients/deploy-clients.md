---
title: Развертывание клиентов для Skype для бизнеса Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Сводка: обзор способов установки корпоративных клиентов для Skype для бизнеса.'
ms.openlocfilehash: cdee3db6dc6fcec646ee2e15b6aeebc298d75b67
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778285"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="7e739-103">Развертывание клиентов для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7e739-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="7e739-104">**Сводка:** Обзор способов установки корпоративных клиентов для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7e739-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="7e739-105">Способ развертывания Skype для бизнеса для пользователей зависит от того, приобрели ли вы Skype для бизнеса в составе плана Office 365 или приобрели Skype для бизнеса с корпоративной лицензией.</span><span class="sxs-lookup"><span data-stu-id="7e739-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="7e739-106">**Office 365** Если у вас есть план Office 365, включающий Skype для бизнеса, то используемая технология установки называется "нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="7e739-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="7e739-107">С помощью Office 365 вы можете разрешить пользователям самостоятельно устанавливать Skype для бизнеса с помощью центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7e739-107">With Office 365, you can let your users install Skype for Business for themselves from the Microsoft 365 admin center.</span></span> <span data-ttu-id="7e739-108">Вы также можете развернуть Skype для бизнеса для пользователей, загрузив программное обеспечение в локальную сеть, а затем используя существующие средства развертывания программного обеспечения, например с помощью диспетчера конфигураций конечных точек Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="7e739-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="7e739-109">Сведения об установке Skype для бизнеса, поступающих в Office 365, можно найти [в статье Развертывание клиента Skype для бизнеса в office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="7e739-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="7e739-110">**Корпоративная лицензия** Если вы используете версию клиента Skype для бизнеса 2015 или 2016 с корпоративной лицензией, используемая технология установки — установщик Windows (MSI).</span><span class="sxs-lookup"><span data-stu-id="7e739-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="7e739-111">Пакет установки на основе установщика Windows состоит из нескольких MSI файлов.</span><span class="sxs-lookup"><span data-stu-id="7e739-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="7e739-112">Не зависящий от языка основной пакет MSI объединен с одним или несколькими языковыми пакетами, что в совокупности и представляет полный продукт.</span><span class="sxs-lookup"><span data-stu-id="7e739-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="7e739-113">При настройке отдельные пакеты собираются вместе и выполняются задачи настройки и обслуживания во время и после установки Office на пользовательские компьютеры.</span><span class="sxs-lookup"><span data-stu-id="7e739-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="7e739-114">В клиенте Skype для бизнеса 2019 используются установщики "нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="7e739-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="7e739-115">В подразделах этого раздела описывается, как использовать и настраивать установщик Windows для развертывания клиента Skype для бизнеса для пользователей с помощью обычных процедур.</span><span class="sxs-lookup"><span data-stu-id="7e739-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7e739-116">Надстройка "собрание Skype" для Microsoft Office, которая поддерживает управление собраниями в клиенте обмена сообщениями и совместной работы Outlook, устанавливается автоматически с клиентами Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7e739-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7e739-117">Программа установки Office 365 не удаляет предыдущие версии Lync.</span><span class="sxs-lookup"><span data-stu-id="7e739-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="7e739-118">Клиент Skype для бизнеса устанавливается параллельно с другими клиентами Lync.</span><span class="sxs-lookup"><span data-stu-id="7e739-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="7e739-119">Установка клиентов Windows</span><span class="sxs-lookup"><span data-stu-id="7e739-119">Installing Windows clients</span></span>

- [<span data-ttu-id="7e739-120">Настройка установки клиента Windows в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7e739-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="7e739-121">Настройка взаимодействия с клиентом с помощью Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7e739-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="7e739-122">Настройка списка смарт-контактов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7e739-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="7e739-123">Установка клиентов устройств</span><span class="sxs-lookup"><span data-stu-id="7e739-123">Installing device clients</span></span>

- [<span data-ttu-id="7e739-124">Установка и тестирование Skype для бизнеса для Windows Phone</span><span class="sxs-lookup"><span data-stu-id="7e739-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="7e739-125">Установка и тестирование Skype для бизнеса для iOS</span><span class="sxs-lookup"><span data-stu-id="7e739-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="7e739-126">Развертывание подключаемого модуля VDI для Lync с помощью Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7e739-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="7e739-127">Развертывание веб-клиентов, загружаемых через Интернет, в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7e739-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="7e739-128">Настройка взаимодействия с клиентом Mac в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7e739-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="7e739-129">См. также</span><span class="sxs-lookup"><span data-stu-id="7e739-129">See also</span></span>

[<span data-ttu-id="7e739-130">Развертывание клиента Skype для бизнеса в Office 365</span><span class="sxs-lookup"><span data-stu-id="7e739-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
