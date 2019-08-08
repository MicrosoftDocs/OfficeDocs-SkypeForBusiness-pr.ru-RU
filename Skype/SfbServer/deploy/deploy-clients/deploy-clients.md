---
title: Развертывание клиентов для Skype для бизнеса Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Сводка: Общие сведения о методах установки корпоративных клиентов для Skype для бизнеса.'
ms.openlocfilehash: f40a4948deb495998debd033f449d9439fd8329b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234132"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="32e57-103">Развертывание клиентов для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="32e57-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="32e57-104">**Сводка:** Общие сведения о методах установки корпоративных клиентов для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="32e57-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="32e57-105">Способ развертывания Skype для бизнеса для пользователей зависит от того, приобрели ли вы Skype для бизнеса как часть плана Office 365 или вы приобрели корпоративную версию Skype для бизнеса с корпоративной лицензией.</span><span class="sxs-lookup"><span data-stu-id="32e57-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="32e57-106">**Office 365** Если вы используете план Office 365, включающий Skype для бизнеса, используется технология установки, которая называется "нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="32e57-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="32e57-107">С помощью Office 365 вы можете установить Skype для бизнеса для пользователей на портале Office 365.</span><span class="sxs-lookup"><span data-stu-id="32e57-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="32e57-108">Кроме того, вы можете развернуть Skype для бизнеса для пользователей, загрузив программное обеспечение в локальную сеть, а затем используя существующие средства развертывания программного обеспечения, например Microsoft System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="32e57-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="32e57-109">Сведения об установке Skype для бизнеса, которые поставляются вместе с Office 365, можно найти [в разделе Развертывание клиента Skype для бизнеса в office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="32e57-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="32e57-110">**Корпоративное лицензирование** Если у вас есть лицензированная Корпоративная версия клиента Skype для бизнеса 2015 или 2016, используется технология установки, которая является установщиком Windows (MSI).</span><span class="sxs-lookup"><span data-stu-id="32e57-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="32e57-111">Пакет установки на основе установщика Windows состоит из нескольких MSI-файлов.</span><span class="sxs-lookup"><span data-stu-id="32e57-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="32e57-112">Не зависящий от языка основной пакет MSI объединен с одним или несколькими языковыми пакетами, что в совокупности и представляет полный продукт.</span><span class="sxs-lookup"><span data-stu-id="32e57-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="32e57-113">При настройке отдельные пакеты собираются вместе и выполняются задачи настройки и обслуживания во время и после установки Office на пользовательские компьютеры.</span><span class="sxs-lookup"><span data-stu-id="32e57-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="32e57-114">В клиенте Skype для бизнеса 2019 используются установщики "нажми и работай".</span><span class="sxs-lookup"><span data-stu-id="32e57-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="32e57-115">В этом разделе описано использование и Настройка установщика Windows для развертывания клиента Skype для бизнеса для пользователей с помощью обычных процедур.</span><span class="sxs-lookup"><span data-stu-id="32e57-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="32e57-116">Надстройка "собрание Skype" для Microsoft Office, поддерживающая управление собраниями в клиенте обмена сообщениями и совместной работы в Outlook, устанавливается автоматически с помощью клиентов Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="32e57-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="32e57-117">Программа установки Office 365 не удаляет предыдущие версии Lync.</span><span class="sxs-lookup"><span data-stu-id="32e57-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="32e57-118">Клиент Skype для бизнеса устанавливается рядом с другими клиентами Lync.</span><span class="sxs-lookup"><span data-stu-id="32e57-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="32e57-119">Установка клиентов Windows</span><span class="sxs-lookup"><span data-stu-id="32e57-119">Installing Windows clients</span></span>

- [<span data-ttu-id="32e57-120">Настройка установки клиента Windows в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="32e57-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="32e57-121">Настройка взаимодействия с клиентом в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="32e57-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="32e57-122">Настройка интеллектуального списка контактов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="32e57-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="32e57-123">Установка клиентов устройства</span><span class="sxs-lookup"><span data-stu-id="32e57-123">Installing device clients</span></span>

- [<span data-ttu-id="32e57-124">Install and test Skype for Business for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="32e57-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="32e57-125">Install and test Skype for Business for iOS</span><span class="sxs-lookup"><span data-stu-id="32e57-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="32e57-126">Развертывание плагина Lync VDI с помощью Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="32e57-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="32e57-127">Развертывание загружаемых веб-клиентов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="32e57-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="32e57-128">Настройка клиента на Mac в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="32e57-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="32e57-129">См. также</span><span class="sxs-lookup"><span data-stu-id="32e57-129">See also</span></span>

[<span data-ttu-id="32e57-130">Развертывание клиента Skype для бизнеса в Office 365</span><span class="sxs-lookup"><span data-stu-id="32e57-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
