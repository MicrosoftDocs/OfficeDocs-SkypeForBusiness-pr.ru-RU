---
title: 'Lync Server 2013: использование центра развертывания Office (OCT)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04cf51d16c27a75d65b1936f2f95e1e5865ad63e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42116762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a><span data-ttu-id="683a6-102">Использование центра развертывания Office (OCT) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="683a6-102">Using the Office Customization Tool (OCT) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="683a6-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="683a6-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="683a6-104">Центр развертывания Office входит в состав программы установки и является рекомендованным средством для многих видов настройки.</span><span class="sxs-lookup"><span data-stu-id="683a6-104">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="683a6-105">С помощью центра развертывания Office можно настроить Office и сохранить настройки установки в MSP-файле.</span><span class="sxs-lookup"><span data-stu-id="683a6-105">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="683a6-106">Этот файл можно поместить в папку "Updates" в точке сетевой установки.</span><span class="sxs-lookup"><span data-stu-id="683a6-106">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="683a6-107">Во время установки Office программа установки выполняет поиск файла настроек установки в папке "Updates" и применяет эти настройки.</span><span class="sxs-lookup"><span data-stu-id="683a6-107">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="683a6-108">Папку Updates можно использовать только для развертывания обновлений программного обеспечения во время первоначальной установки Office 2013.</span><span class="sxs-lookup"><span data-stu-id="683a6-108">The Updates folder can be used only to deploy software updates during an initial installation of Office 2013.</span></span>

<span data-ttu-id="683a6-109">Центр развертывания Office является частью программы установки и включается в версии продукта с лицензией для многократной установки.</span><span class="sxs-lookup"><span data-stu-id="683a6-109">The OCT is part of setup and it is included in volume license versions of the product.</span></span> <span data-ttu-id="683a6-110">Чтобы запустить центр развертывания Office, `setup.exe /admin` введите в командной строке корневой каталог точки сетевой установки, содержащей исходные файлы Office 2013.</span><span class="sxs-lookup"><span data-stu-id="683a6-110">You run the OCT by typing `setup.exe /admin` at the command line from the root of the network installation point that contains the Office 2013 source files.</span></span> <span data-ttu-id="683a6-111">Например, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="683a6-111">For example, use the following:</span></span>

`\\server\share\Office15\setup.exe /admin`

<span data-ttu-id="683a6-112">С помощью центра развертывания Office администратор может создать и настроить MSP-файл с настройками установки.</span><span class="sxs-lookup"><span data-stu-id="683a6-112">Administrators use the OCT to create a setup customization .msp file.</span></span> <span data-ttu-id="683a6-113">Как и в центре развертывания Microsoft Office 2010, администраторы могут настраивать следующие области:</span><span class="sxs-lookup"><span data-stu-id="683a6-113">As in the Microsoft Office 2010 OCT, administrators can customize the following areas:</span></span>

  - <span data-ttu-id="683a6-114">**Настройка** Используется для указания места установки по умолчанию на клиенте и имени Организации по умолчанию, дополнительных источников сетевой установки, ключа продукта, лицензионного соглашения, уровня отображения, более ранних версий Office для удаления, настраиваемых программ, выполняемых во время установки, параметров безопасности и свойств установки.</span><span class="sxs-lookup"><span data-stu-id="683a6-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>

  - <span data-ttu-id="683a6-115">**Компоненты** Используется для настройки параметров пользователя и настройки способа установки компонентов Office.</span><span class="sxs-lookup"><span data-stu-id="683a6-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="683a6-116">С помощью центра развертывания Office администратор может указать первоначальные значения по умолчанию для пользовательских параметров приложений Office.</span><span class="sxs-lookup"><span data-stu-id="683a6-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="683a6-117">После установки пользователи могут изменить большинство из этих параметров.</span><span class="sxs-lookup"><span data-stu-id="683a6-117">Users can modify most of the settings after the installation.</span></span>

  - <span data-ttu-id="683a6-118">**Дополнительные материалы** Используется для добавления и удаления файлов, добавления и удаления записей реестра, а также настройки ярлыков.</span><span class="sxs-lookup"><span data-stu-id="683a6-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>

  - <span data-ttu-id="683a6-119">**Outlook** Используется для настройки профиля пользователя, используемого по умолчанию в Outlook, указания параметров Exchange, добавления учетных записей, удаления учетных записей\\и параметров экспорта и указания групп получения отправки.</span><span class="sxs-lookup"><span data-stu-id="683a6-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\\Receive groups.</span></span>

<span data-ttu-id="683a6-120">Информация о центре развертывания Office приведена <https://go.microsoft.com/fwlink/p/?linkid=267516>в разделе.</span><span class="sxs-lookup"><span data-stu-id="683a6-120">For information about the OCT, see <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

