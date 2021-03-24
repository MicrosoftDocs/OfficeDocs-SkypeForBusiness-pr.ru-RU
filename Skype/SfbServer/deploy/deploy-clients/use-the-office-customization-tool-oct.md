---
title: Используйте средство настройки Office (OCT) в Skype для бизнеса Server
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
ms.openlocfilehash: 32cd7951690ce5b1e38c20d83c8f53a9c48cd19c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100455"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="07c81-103">Используйте средство настройки Office (OCT) в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="07c81-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="07c81-104">**Сводка:** Использование средства настройки Office с клиентом Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="07c81-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="07c81-105">Центр развертывания Office входит в состав программы установки и является рекомендованным средством для многих видов настройки.</span><span class="sxs-lookup"><span data-stu-id="07c81-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="07c81-106">С помощью центра развертывания Office можно настроить Office и сохранить настройки установки в MSP-файле.</span><span class="sxs-lookup"><span data-stu-id="07c81-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="07c81-107">Этот файл можно поместить в папку "Updates" в точке сетевой установки.</span><span class="sxs-lookup"><span data-stu-id="07c81-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="07c81-108">Во время установки Office программа установки выполняет поиск файла настроек установки в папке "Updates" и применяет эти настройки.</span><span class="sxs-lookup"><span data-stu-id="07c81-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="07c81-109">Папку Updates можно использовать только для развертывания обновлений программного обеспечения во время начальной установки Office.</span><span class="sxs-lookup"><span data-stu-id="07c81-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="07c81-110">Oct является частью установки и используется только для лицензированных версий продукта.</span><span class="sxs-lookup"><span data-stu-id="07c81-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="07c81-111">Вы запустите ОКТ, введя в командную строку корневую часть точки установки сети, которая  `setup.exe /admin` содержит исходные файлы Office.</span><span class="sxs-lookup"><span data-stu-id="07c81-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="07c81-112">Например, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="07c81-112">For example, use the following:</span></span>
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="07c81-113">Администраторы используют oct для создания файла настройки MSP и могут настроить следующие области:</span><span class="sxs-lookup"><span data-stu-id="07c81-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="07c81-114">**Настройка** Используется для указания расположения установки по умолчанию в имени организации клиента и по умолчанию, дополнительных источников сетевой установки, ключа продукта, лицензионного соглашения конечного пользователя, уровня отображения, более ранних версий Office для удаления, настраиваемые программы для запуска во время установки, параметров безопасности и свойств установки.</span><span class="sxs-lookup"><span data-stu-id="07c81-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="07c81-115">**Функции** Используется для настройки параметров пользователей и настройки установки компонентов Office.</span><span class="sxs-lookup"><span data-stu-id="07c81-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="07c81-116">С помощью центра развертывания Office администратор может указать первоначальные значения по умолчанию для пользовательских параметров приложений Office.</span><span class="sxs-lookup"><span data-stu-id="07c81-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="07c81-117">После установки пользователи могут изменить большинство из этих параметров.</span><span class="sxs-lookup"><span data-stu-id="07c81-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="07c81-118">**Дополнительный контент** Используется для добавления или удаления файлов, добавления или удаления записей реестра и настройки ярлыков.</span><span class="sxs-lookup"><span data-stu-id="07c81-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="07c81-119">**Outlook** Используется для настройки профиля Outlook пользователя по умолчанию, указания параметров Exchange, добавления учетных записей, удаления учетных записей и параметров экспорта и указания групп Send\Receive.</span><span class="sxs-lookup"><span data-stu-id="07c81-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="07c81-120">Сведения о ОК см. в [см. в руб. Использование ОКТ для настройки Office 2013.](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))</span><span class="sxs-lookup"><span data-stu-id="07c81-120">For information about the OCT, see [Use the OCT to customize Office 2013](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="07c81-121">Обратите внимание, что эта информация также применяется к более поздним версиям Office.</span><span class="sxs-lookup"><span data-stu-id="07c81-121">Note that this information also applies to later versions of Office.</span></span>
