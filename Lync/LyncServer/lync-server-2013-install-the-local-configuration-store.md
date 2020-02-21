---
title: 'Lync Server 2013: Установка локального хранилища конфигурации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5c95399aa7cccf28ec0c236c2882b6f44794e80
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a><span data-ttu-id="fef93-102">Установка локального хранилища конфигурации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef93-102">Install the Local Configuration store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fef93-103">_**Последнее изменение темы:** 2014-06-27_</span><span class="sxs-lookup"><span data-stu-id="fef93-103">_**Topic Last Modified:** 2014-06-27_</span></span>

<span data-ttu-id="fef93-104">Перед выполнением этих действий убедитесь, что вы выполнили вход на сервер с учетной записью пользователя домена, который является как локальным администратором, так и членом группы Рткуниверсалреадонлядмин.</span><span class="sxs-lookup"><span data-stu-id="fef93-104">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmin group.</span></span>

<span data-ttu-id="fef93-105">Чтобы иметь возможность выполнять какие-либо действия с мастером развертывания Lync Server, необходимо, чтобы локальное хранилище конфигурации существовало на сервере.</span><span class="sxs-lookup"><span data-stu-id="fef93-105">To be able to do anything with the Lync Server Deployment Wizard, we need the Local Configuration store to exist on a server.</span></span> <span data-ttu-id="fef93-106">Локальное хранилище конфигурации является копией центрального хранилища управления, предназначенной только для чтения, которая создается после локальной установки SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="fef93-106">The Local Configuration store is a read-only copy of the Central Management store, which gets created after the local installation of SQL Server Express.</span></span> <span data-ttu-id="fef93-107">Центральное хранилище управления добавляется в существующую базу данных SQL Server, установленную на сервере Standard Edition или в базе данных на основе SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="fef93-107">The Central Management store itself is added to the existing SQL Server database installed on the Standard Edition server or SQL Server Express-based database.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fef93-108">Если вы еще не выпустили программу установки Lync Server 2013 на этом сервере, вам будет предложено указать диск и путь для установки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fef93-108">If you haven’t run Lync Server 2013 setup on this server before, you’ll be prompted for a drive and path to install Lync Server 2013 to.</span></span> <span data-ttu-id="fef93-109">Это позволит установить на диск, отличный от системного диска, если это требуется в Организации, или если у вас есть проблемы с пространством.</span><span class="sxs-lookup"><span data-stu-id="fef93-109">This will let you install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="fef93-110">Можно просто изменить путь к расположению установки для файлов Lync Server в диалоговом окне программы установки на новый, доступный диск.</span><span class="sxs-lookup"><span data-stu-id="fef93-110">You can just change the installation location path for the Lync Server files in the Setup dialog box to a new, available drive.</span></span> <span data-ttu-id="fef93-111">Если вы устанавливаете файлы установки по этому пути, включая OCSCore. msi, остальные файлы Lync Server 2013 будут развернуты там же.</span><span class="sxs-lookup"><span data-stu-id="fef93-111">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will deploy there as well.</span></span>



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a><span data-ttu-id="fef93-112">Установка хранилища локальной конфигурации</span><span class="sxs-lookup"><span data-stu-id="fef93-112">To install the Local Configuration store</span></span>

1.  <span data-ttu-id="fef93-113">На установочном носителе откройте файл Setup \\.\\exe\\для установки amd64 и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fef93-113">From your installation media, browse to \\setup\\amd64\\Setup.exe, and then click **OK**.</span></span>

2.  <span data-ttu-id="fef93-114">Если вам будет предложено установить распространяемый пакет Microsoft Visual C++ 2012, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="fef93-114">If you’re prompted to install the Microsoft Visual C++ 2012 Redistributable, click **Yes**.</span></span>

3.  <span data-ttu-id="fef93-115">На странице " **Расположение установки Lync Server 2013** " нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fef93-115">On the **Lync Server 2013 Installation Location** page, click **OK**.</span></span>

4.  <span data-ttu-id="fef93-116">На странице Лицензионное **соглашение с конечным пользователем** ознакомьтесь с условиями лицензионного соглашения, а затем выберите **я принимаю условия лицензионного соглашения**, а затем нажмите кнопку **ОК** , чтобы продолжить.</span><span class="sxs-lookup"><span data-stu-id="fef93-116">On the **End User License Agreement** page, review the license terms, you’ll need to select **I accept the terms in the license agreement**, and then click **OK** to be able to continue.</span></span>

5.  <span data-ttu-id="fef93-117">На странице мастера развертывания щелкните **Install or Update Lync Server System** (Установить или обновить Lync Server).</span><span class="sxs-lookup"><span data-stu-id="fef93-117">On the Deployment Wizard page, click **Install or Update Lync Server System**.</span></span>

6.  <span data-ttu-id="fef93-118">На странице **Lync Server 2013** рядом с элементом **Шаг 1: install Local Configuration Store**нажмите кнопку **Run (выполнить**).</span><span class="sxs-lookup"><span data-stu-id="fef93-118">On the **Lync Server 2013** page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

7.  <span data-ttu-id="fef93-119">На странице **Установка локального хранилища конфигурации** убедитесь, что установлен флажок **получить непосредственно из центрального хранилища управления** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="fef93-119">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>

8.  <span data-ttu-id="fef93-120">После завершения установки конфигурации локального сервера нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="fef93-120">When the local server configuration installation is complete, you should click **Finish**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

