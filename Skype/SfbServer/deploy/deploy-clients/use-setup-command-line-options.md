---
title: Использование параметров командной строки при настройке для клиентов Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Сводка: сведения об операциях командной строки Setup. exe в программе установки Office.'
ms.openlocfilehash: 2eee24f9ae79ed2f73e23c68883f2552902fb672
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306484"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="9e926-103">Использование параметров командной строки при настройке для клиентов Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="9e926-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="9e926-104">**Сводка:** Сведения об операциях командной строки Setup. exe в программе установки Office.</span><span class="sxs-lookup"><span data-stu-id="9e926-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="9e926-105">Командная строка программы установки используется для выполнения достаточно редких операций в процессе установки Office.</span><span class="sxs-lookup"><span data-stu-id="9e926-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="9e926-106">Вместо использования параметров командной строки для настройки вы обычно используете средство настройки Office и файл config. XML для настройки продуктов и функций.</span><span class="sxs-lookup"><span data-stu-id="9e926-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="9e926-107">Командная строка программы установки Office распознает параметры командной строки, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="9e926-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="9e926-108">**Параметры командной строки программы установки Office**</span><span class="sxs-lookup"><span data-stu-id="9e926-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="9e926-109">**Параметр командной строки программы установки**</span><span class="sxs-lookup"><span data-stu-id="9e926-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="9e926-110">**Описание**</span><span class="sxs-lookup"><span data-stu-id="9e926-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9e926-111">/admin</span><span class="sxs-lookup"><span data-stu-id="9e926-111">/admin</span></span>  <br/> |<span data-ttu-id="9e926-112">Запускает центр развертывания Office для создания файла настройки программы установки (файла MSP).</span><span class="sxs-lookup"><span data-stu-id="9e926-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="9e926-113">/adminfile [путь]</span><span class="sxs-lookup"><span data-stu-id="9e926-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="9e926-p102">Применяет к установке указанный файл настройки программы установки. Можно указать путь к конкретному MSP-файлу настройки или к папке файлов настройки.</span><span class="sxs-lookup"><span data-stu-id="9e926-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="9e926-116">/config [путь]</span><span class="sxs-lookup"><span data-stu-id="9e926-116">/config [path]</span></span>  <br/> |<span data-ttu-id="9e926-117">Указывает файл Config.xml, который программа установки использует во время установки.</span><span class="sxs-lookup"><span data-stu-id="9e926-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="9e926-118">Используйте параметр/config для указания файла config. XML, настроенного для установки Skype для бизнеса, например:`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="9e926-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="9e926-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="9e926-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="9e926-120">Используется с модифицированным файлом Config.xml для запуска программы установки в режиме обслуживания и изменения существующей установки Office.</span><span class="sxs-lookup"><span data-stu-id="9e926-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="9e926-121">Например, вы можете использовать параметр/модифи для добавления или удаления функций Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9e926-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="9e926-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="9e926-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="9e926-123">Запускает программу установки с компьютера пользователя для восстановления Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="9e926-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="9e926-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="9e926-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="9e926-125">Запускает программу установки для удаления Skype для бизнеса с компьютера пользователя.</span><span class="sxs-lookup"><span data-stu-id="9e926-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


