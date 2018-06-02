---
title: Развертывание клиентов для Skype для бизнеса Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Сводка: Обзор методов установки enterprise client для Скайп для бизнеса.'
ms.openlocfilehash: 4c1253613befd5bf71add33b7ab9cab826d4a490
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2018
ms.locfileid: "19546471"
---
# <a name="deploy-clients-for-skype-for-business-server-2015"></a><span data-ttu-id="dc043-103">Развертывание клиентов для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="dc043-103">Deploy clients for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dc043-104">**Сводка:** Обзор корпоративных клиентов методы Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="dc043-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="dc043-105">Как развернуть Скайп для бизнеса для пользователей зависит от того, является ли вы приобрели Скайп для бизнеса в рамках плана Office 365 или приобрести лицензированную версию тома Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="dc043-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="dc043-106">**Office 365** Если у вас есть план Office 365, которая включает в себя Скайп для бизнеса, технология установки, которая используется называется Click-to-Run.</span><span class="sxs-lookup"><span data-stu-id="dc043-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="dc043-107">В Office 365 можно позволить пользователям установить Скайп для бизнеса на свои компьютеры с портала Office 365.</span><span class="sxs-lookup"><span data-stu-id="dc043-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="dc043-108">Или Скайп для бизнеса можно развернуть для пользователей, загрузив программное обеспечение в локальную сеть и затем с помощью существующие средства развертывания программного обеспечения, например, с помощью Microsoft System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="dc043-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="dc043-109">Сведения об установке о Скайп для бизнеса с Office 365 см [Скайп для клиента бизнеса в Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="dc043-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="dc043-110">**Том с корпоративным лицензированием** Если у вас есть корпоративной лицензии ОС Скайп для бизнеса, технология установки, которая используется — установщика Windows (MSI).</span><span class="sxs-lookup"><span data-stu-id="dc043-110">**Volume licensed** If you have a volume licensed version of Skype for Business, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="dc043-111">Пакет установки на основе установщика Windows состоит из нескольких файлов MSI.</span><span class="sxs-lookup"><span data-stu-id="dc043-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="dc043-112">Не зависящий от языка основной пакет MSI объединен с одним или несколькими языковыми пакетами, что в совокупности и представляет полный продукт.</span><span class="sxs-lookup"><span data-stu-id="dc043-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="dc043-113">При настройке отдельные пакеты собираются вместе и выполняются задачи настройки и обслуживания во время и после установки Office на пользовательские компьютеры.</span><span class="sxs-lookup"><span data-stu-id="dc043-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span>
    
<span data-ttu-id="dc043-114">В этом разделе описываются способы использования и настройки установщика Windows для развертывания Скайп для клиента Business для пользователей с помощью обычного процедур.</span><span class="sxs-lookup"><span data-stu-id="dc043-114">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc043-115">Online собрания надстройки для Скайп для бизнеса, который поддерживает собрания управления из приложения Outlook клиент обмена сообщениями и совместной работы, автоматическая установка вместе с Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="dc043-115">The Online meeting Add-in for Skype for Business, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="dc043-116">Программа установки Office 365 не приводит к удалению предыдущих версий Lync или Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="dc043-116">The Office 365 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="dc043-117">Скайп для клиента Business устанавливает рядом с другими клиентами Lync или Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="dc043-117">The Skype for Business client installs side-by-side with other Lync or Office Communicator clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="dc043-118">Установка клиентов Windows</span><span class="sxs-lookup"><span data-stu-id="dc043-118">Installing Windows clients</span></span>

- [<span data-ttu-id="dc043-119">Настройка установки клиента Windows в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dc043-119">Customize Windows client installation in Skype for Business Server 2015</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="dc043-120">Настройка взаимодействия с пользователем с помощью Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="dc043-120">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="dc043-121">Настройка списка смарт-контактов в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="dc043-121">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="dc043-122">Установка устройства клиентов</span><span class="sxs-lookup"><span data-stu-id="dc043-122">Installing device clients</span></span>

- [<span data-ttu-id="dc043-123">Установка и тестирование Скайп для бизнеса для Windows Phone</span><span class="sxs-lookup"><span data-stu-id="dc043-123">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="dc043-124">Установка и тестирование Скайп для бизнеса для операций ввода-вывода</span><span class="sxs-lookup"><span data-stu-id="dc043-124">Install and test Skype for Business for iOS</span></span>](ios.md)
    
- [<span data-ttu-id="dc043-125">Развертывание системы Скайп помещения в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="dc043-125">Deploy Skype Room System in Skype for Business Server</span></span>](deploy-skype-room-system.md)
    
- [<span data-ttu-id="dc043-126">Развертывание Скайп комнаты систем версии 2</span><span class="sxs-lookup"><span data-stu-id="dc043-126">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
    
- [<span data-ttu-id="dc043-127">Развертывание подключаемого модуля VDI Lync с Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dc043-127">Deploy the Lync VDI plug-in with Skype for Business Server 2015</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="dc043-128">Развертывание веб-загрузки клиентов в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dc043-128">Deploy Web downloadable clients in Skype for Business Server 2015</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="dc043-129">Настройка взаимодействия с пользователем Mac в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="dc043-129">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="dc043-130">См. также</span><span class="sxs-lookup"><span data-stu-id="dc043-130">See also</span></span>

[<span data-ttu-id="dc043-131">Развертывание Скайп для клиента бизнеса в Office 365</span><span class="sxs-lookup"><span data-stu-id="dc043-131">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)