---
title: Использование средства развертывания Office (OCT) в Skype для бизнеса Server
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
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Сводка: использование средства настройки Office в клиенте Skype для бизнеса.'
ms.openlocfilehash: d5b9e5363f56842675831c4b3c0fe3582fb6d02a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768452"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="6e128-103">Использование средства развертывания Office (OCT) в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6e128-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="6e128-104">**Сводка:** Использование средства настройки Office в клиенте Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="6e128-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="6e128-105">Центр развертывания Office входит в состав программы установки и является рекомендованным средством для многих видов настройки.</span><span class="sxs-lookup"><span data-stu-id="6e128-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="6e128-106">С помощью центра развертывания Office можно настроить Office и сохранить настройки установки в MSP-файле.</span><span class="sxs-lookup"><span data-stu-id="6e128-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="6e128-107">Этот файл можно поместить в папку "Updates" в точке сетевой установки.</span><span class="sxs-lookup"><span data-stu-id="6e128-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="6e128-108">Во время установки Office программа установки выполняет поиск файла настроек установки в папке "Updates" и применяет эти настройки.</span><span class="sxs-lookup"><span data-stu-id="6e128-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="6e128-109">Папку Updates можно использовать только для развертывания обновлений программного обеспечения во время первоначальной установки Office.</span><span class="sxs-lookup"><span data-stu-id="6e128-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="6e128-110">Параметр OCT является частью настройки и используется только для корпоративных версий продукта.</span><span class="sxs-lookup"><span data-stu-id="6e128-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="6e128-111">Чтобы запустить приложение OCT, введите `setup.exe /admin` в командной строке корень точки сетевой установки, содержащей исходные файлы Office.</span><span class="sxs-lookup"><span data-stu-id="6e128-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="6e128-112">Например, используйте следующий путь.</span><span class="sxs-lookup"><span data-stu-id="6e128-112">For example, use the following:</span></span>
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="6e128-113">Администраторы используют OCT для создания файла параметров настройки Setup. MSP и могут настраивать следующие области:</span><span class="sxs-lookup"><span data-stu-id="6e128-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="6e128-114">**Настройка** Используется для указания местоположения для установки по умолчанию на клиенте и названии организации по умолчанию, дополнительные источники сетевой установки, ключ продукта, лицензионное соглашение с конечным пользователем, уровень отображения и более ранние версии Office для удаления, пользовательские программы для запуска во время установки, параметры безопасности и свойства настройки.</span><span class="sxs-lookup"><span data-stu-id="6e128-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="6e128-115">**Функции** Используется для настройки параметров пользователя и для настройки способа установки компонентов Office.</span><span class="sxs-lookup"><span data-stu-id="6e128-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="6e128-116">С помощью центра развертывания Office администратор может указать первоначальные значения по умолчанию для пользовательских параметров приложений Office.</span><span class="sxs-lookup"><span data-stu-id="6e128-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="6e128-117">После установки пользователи могут изменить большинство из этих параметров.</span><span class="sxs-lookup"><span data-stu-id="6e128-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="6e128-118">**Дополнительное содержимое** Используется для добавления и удаления файлов, добавления и удаления записей в реестре, а также для настройки сочетаний клавиш.</span><span class="sxs-lookup"><span data-stu-id="6e128-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="6e128-119">**Приложение Outlook** Используется для настройки профиля пользователя Outlook по умолчанию, указания параметров Exchange, добавления учетных записей, удаления учетных записей и экспорта параметров и задания групп Сенд\рецеиве.</span><span class="sxs-lookup"><span data-stu-id="6e128-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="6e128-120">Сведения о программе OCT можно найти в разделе [Использование OCT для настройки Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span><span class="sxs-lookup"><span data-stu-id="6e128-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="6e128-121">Обратите внимание, что эта информация также относится к более поздним версиям Office.</span><span class="sxs-lookup"><span data-stu-id="6e128-121">Note that this information also applies to later versions of Office.</span></span>
  

