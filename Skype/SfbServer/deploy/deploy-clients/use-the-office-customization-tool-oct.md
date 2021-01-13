---
title: Использование средства настройки Office (OCT) в Skype для бизнеса Server
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
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: Сводка. Использование средства настройки Office с клиентом Skype для бизнеса.
ms.openlocfilehash: ba99f0556f3fb1d0e0f6870d1eaa7a3d2108b4d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812569"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="097d4-103">Использование средства настройки Office (OCT) в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="097d4-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="097d4-104">**Сводка:** Использование средства настройки Office с клиентом Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="097d4-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="097d4-105">Центр развертывания Office входит в состав программы установки и является рекомендованным средством для многих видов настройки.</span><span class="sxs-lookup"><span data-stu-id="097d4-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="097d4-106">С помощью центра развертывания Office можно настроить Office и сохранить настройки установки в MSP-файле.</span><span class="sxs-lookup"><span data-stu-id="097d4-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="097d4-107">Этот файл можно поместить в папку "Updates" в точке сетевой установки.</span><span class="sxs-lookup"><span data-stu-id="097d4-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="097d4-108">Во время установки Office программа установки выполняет поиск файла настроек установки в папке "Updates" и применяет эти настройки.</span><span class="sxs-lookup"><span data-stu-id="097d4-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="097d4-109">Папку Updates можно использовать только для развертывания обновлений программного обеспечения во время начальной установки Office.</span><span class="sxs-lookup"><span data-stu-id="097d4-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="097d4-110">Oct является частью программы установки и используется только для версий продукта с много лицензиями.</span><span class="sxs-lookup"><span data-stu-id="097d4-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="097d4-111">Чтобы запустить oct, введите в командной строке корневой папки точки сетевой установки,  `setup.exe /admin` содержаной исходные файлы Office.</span><span class="sxs-lookup"><span data-stu-id="097d4-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="097d4-112">Например, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="097d4-112">For example, use the following:</span></span>
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="097d4-113">Администраторы используют oct для создания MSP-файла настройки установки и могут настраивать следующие области:</span><span class="sxs-lookup"><span data-stu-id="097d4-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="097d4-114">**Настройка** Используется для указания расположения установки по умолчанию для имени клиента и организации по умолчанию, дополнительных источников сетевой установки, ключа продукта, лицензионного соглашения с конечным пользователем, уровня отображения, удаляемого более ранних версий Office, пользовательских программ, запускаемые во время установки, параметров безопасности и свойств установки.</span><span class="sxs-lookup"><span data-stu-id="097d4-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="097d4-115">**Функции** Используется для настройки пользовательских параметров и настройки установки компонентов Office.</span><span class="sxs-lookup"><span data-stu-id="097d4-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="097d4-116">С помощью центра развертывания Office администратор может указать первоначальные значения по умолчанию для пользовательских параметров приложений Office.</span><span class="sxs-lookup"><span data-stu-id="097d4-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="097d4-117">После установки пользователи могут изменить большинство из этих параметров.</span><span class="sxs-lookup"><span data-stu-id="097d4-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="097d4-118">**Дополнительное содержимое** Используется для добавления или удаления файлов, добавления или удаления записей реестра и настройки ярлыков.</span><span class="sxs-lookup"><span data-stu-id="097d4-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="097d4-119">**Outlook** Используется для настройки профиля Outlook пользователя по умолчанию, указания параметров Exchange, добавления учетных записей, удаления учетных записей и параметров экспорта, а также для указания групп отправки и получения.</span><span class="sxs-lookup"><span data-stu-id="097d4-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="097d4-120">Сведения о oct см. в подстройке [Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))с помощью oct.</span><span class="sxs-lookup"><span data-stu-id="097d4-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="097d4-121">Обратите внимание, что эти сведения также относятся к более поздним версиям Office.</span><span class="sxs-lookup"><span data-stu-id="097d4-121">Note that this information also applies to later versions of Office.</span></span>
  

