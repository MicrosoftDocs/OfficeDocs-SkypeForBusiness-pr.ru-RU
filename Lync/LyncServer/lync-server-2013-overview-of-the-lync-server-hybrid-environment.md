---
title: 'Lync Server 2013: обзор гибридной среды Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f99aeda6136c79b7ffda9b5cd3d5dced3b1f6ee4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516116"
---
# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a><span data-ttu-id="e47aa-102">Обзор гибридной среды Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e47aa-102">Overview of the Lync Server 2013 hybrid environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e47aa-103">_**Последнее изменение темы:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="e47aa-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="e47aa-104">Гибридная Среда Lync Server 2013 относится к развертыванию, в котором есть некоторые пользователи, размещенные на локальном сервере Lync Server 2013 и другие пользователи, размещенные в Lync Online, но пользователи используют один и тот же домен, например user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e47aa-104">Lync Server 2013 hybrid environment refers to a deployment in which there are some users homed to the on-premises Lync Server 2013 and other users homed to Lync Online, but users share the same domain, such as user@contoso.com.</span></span>

<div>

## <a name="about-this-guide"></a><span data-ttu-id="e47aa-105">Сведения о данном руководстве</span><span class="sxs-lookup"><span data-stu-id="e47aa-105">About this Guide</span></span>

<span data-ttu-id="e47aa-106">В этом руководстве описываются задачи, необходимые для настройки среды Lync Server 2013 для взаимодействия с Lync Online, а также перемещения пользователей из локального развертывания для использования Lync Online.</span><span class="sxs-lookup"><span data-stu-id="e47aa-106">This guide describes the tasks necessary to configure your Lync Server 2013 environment for interoperability with Lync Online, and then to move users from your on-premises deployment to use Lync Online.</span></span>

</div>

<div>

## <a name="prerequisites"></a><span data-ttu-id="e47aa-107">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="e47aa-107">Prerequisites</span></span>

<span data-ttu-id="e47aa-108">Для выполнения задач, необходимых для настройки развертывания гибридной среды, необходимо установить следующие приложения и служебные программы.</span><span class="sxs-lookup"><span data-stu-id="e47aa-108">You will need to have the following applications and utilities installed to complete the tasks for configuring a deployment for hybrid.</span></span> <span data-ttu-id="e47aa-109">Установщики для этих файлов находятся на установочном носителе, предоставленном вам для развертывания, а также по ссылкам в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="e47aa-109">The installers for these files are included on the installation media provided for your deployment, as well as at the links included in the following list.</span></span>

  - [<span data-ttu-id="e47aa-110">Службы федерации Active Directory (AD FS) 2.0</span><span class="sxs-lookup"><span data-stu-id="e47aa-110">Active Directory Federation Services (AD FS) 2.0</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257305)

  - [<span data-ttu-id="e47aa-111">Средство синхронизации каталогов (Майкрософт) 9,1</span><span class="sxs-lookup"><span data-stu-id="e47aa-111">Microsoft Directory Synchronization Tool 9.1</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257307)

  - [<span data-ttu-id="e47aa-112">Установка Windows PowerShell для единого входа с помощью AD FS</span><span class="sxs-lookup"><span data-stu-id="e47aa-112">Install Windows PowerShell for single sign-on with AD FS</span></span>](https://go.microsoft.com/fwlink/p/?linkid=398710)

  - <span data-ttu-id="e47aa-113">Помощник по входу в Microsoft Online Services (msoidcli-7.0.msi) включен в настройку настольного компьютера для Microsoft 365, которую можно получить на странице Загружаемые файлы, связанную с центром администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e47aa-113">Microsoft Online Services Sign-in Assistant (msoidcli-7.0.msi) is included with the Desktop Setup for Microsoft 365, which can be obtained from the Downloads page linked to from the Microsoft 365 admin center.</span></span>

</div>

<div>

## <a name="administrator-credentials"></a><span data-ttu-id="e47aa-114">Учетные данные администратора</span><span class="sxs-lookup"><span data-stu-id="e47aa-114">Administrator Credentials</span></span>

<span data-ttu-id="e47aa-115">Когда вам будет предложено ввести учетные данные администратора, укажите имя пользователя и пароль для учетной записи администратора вашей организации Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="e47aa-115">When you are asked to provide your administrator credentials, use the username and password for the administrator account for your Microsoft 365 or Office 365 organization.</span></span> <span data-ttu-id="e47aa-116">Эти учетные данные также будут использоваться при настройке служб федерации Active Directory (AD FS) 2,0, синхронизации каталогов, единого входа, Федерации и перемещения пользователей в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="e47aa-116">You will also use these credentials when you configure Active Directory Federation Services (AD FS) 2.0, Directory Synchronization, Single sign-on, federation, and moving users to Lync Online.</span></span>

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a><span data-ttu-id="e47aa-117">Подключение к Lync Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e47aa-117">Connecting to Lync Online PowerShell</span></span>

<span data-ttu-id="e47aa-118">Теперь администраторы могут использовать Windows PowerShell для управления Lync Online и учетными записями пользователей Lync Online.</span><span class="sxs-lookup"><span data-stu-id="e47aa-118">Administrators now have the ability to use Windows PowerShell to manage Lync Online and their Lync Online user accounts.</span></span> <span data-ttu-id="e47aa-119">Для этого необходимо сначала скачать и установить модуль соединителя Lync Online в центре загрузки Майкрософт ( https://go.microsoft.com/fwlink/?LinkId=294688) .</span><span class="sxs-lookup"><span data-stu-id="e47aa-119">To do this, you must first download and install the Lync Online Connector Module from the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="e47aa-120">Дополнительные сведения о загрузке, установке и использовании модуля соединителя Lync Online и подробные сведения об использовании Windows PowerShell для управления Lync Online приведены в статье [Использование Windows PowerShell для управления Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="e47aa-120">For more information on downloading, installing, and using the Lync Online Connector Module, and for detailed information on using Windows PowerShell to manage Lync Online, see [Using Windows PowerShell to manage Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

