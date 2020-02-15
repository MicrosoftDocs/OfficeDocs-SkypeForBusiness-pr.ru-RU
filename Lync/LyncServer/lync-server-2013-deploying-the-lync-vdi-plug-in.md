---
title: 'Lync Server 2013: Развертывание подключаемого модуля VDI для Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync VDI plug-in
ms:assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204683(v=OCS.15)
ms:contentKeyID: 48183449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6802be2d2191c057e35ac25618d74c1e338899a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="e2e02-102">Развертывание подключаемого модуля VDI для Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2e02-102">Deploying the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2e02-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e2e02-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e2e02-104">Клиент Lync 2013 поддерживает аудио и видео в среде инфраструктуры виртуальных рабочих столов (VDI).</span><span class="sxs-lookup"><span data-stu-id="e2e02-104">The Lync 2013 client supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="e2e02-105">Пользователь может подключить аудио- или видеоустройство (например, гарнитуру или камеру) к локальному компьютеру (например, к тонкому клиенту или используемому в качестве такового старому компьютеру).</span><span class="sxs-lookup"><span data-stu-id="e2e02-105">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="e2e02-106">Пользователь может подключиться к виртуальной машине, войти в клиент Lync 2013, запущенный на виртуальной машине, и участвовать в голосовой и видеосвязи в режиме реального времени, как будто клиент запущен на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e2e02-106">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communications as though the client is running locally.</span></span>

<span data-ttu-id="e2e02-107">Подключаемый модуль VDI для Lync — это автономное приложение, устанавливаемое на локальном компьютере и позволяющее использовать локальные аудио-и видеоустройства с клиентом Lync 2013, запущенным на виртуальной машине.</span><span class="sxs-lookup"><span data-stu-id="e2e02-107">The Lync VDI Plug-in is a stand-alone application that installs on the local computer and allows the use of local audio and video devices with the Lync 2013 client running on the virtual machine.</span></span> <span data-ttu-id="e2e02-108">Для подключаемого модуля не требуется установка Lync на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e2e02-108">The plug-in does not require Lync to be installed on the local computer.</span></span> <span data-ttu-id="e2e02-109">После того как пользователь войдет в клиент Lync 2013, запущенный на виртуальной машине, Lync предложит пользователю повторно ввести свои учетные данные, чтобы установить подключение к подключаемому модулю Lync VDI, запущенному на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="e2e02-109">After the user signs in to the Lync 2013 client that is running on the virtual machine, Lync prompts the user to re-enter his or her credentials to establish a connection with the Lync VDI Plug-in that is running on the local computer.</span></span> <span data-ttu-id="e2e02-110">После того как это подключение установлено, пользователь готов выполнять и принимать аудио- и видеовызовы.</span><span class="sxs-lookup"><span data-stu-id="e2e02-110">After this connection is established, the user is ready to make and receive audio and video calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e2e02-111">Содержание этого раздела</span><span class="sxs-lookup"><span data-stu-id="e2e02-111">In This Section</span></span>

  - [<span data-ttu-id="e2e02-112">Необходимые условия для подключаемого модуля Lync VDI в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2e02-112">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>](lync-server-2013-lync-vdi-plug-in-prerequisites.md)

  - [<span data-ttu-id="e2e02-113">Подготовка среды Lync Server 2013 для VDI</span><span class="sxs-lookup"><span data-stu-id="e2e02-113">Preparing your Lync Server 2013 environment for VDI</span></span>](lync-server-2013-preparing-your-environment-for-vdi.md)

  - [<span data-ttu-id="e2e02-114">Вход на виртуальную машину и использование Lync 2013</span><span class="sxs-lookup"><span data-stu-id="e2e02-114">Signing in and using Lync 2013 on the virtual machine</span></span>](lync-server-2013-signing-in-and-using-lync-2013-on-the-virtual-machine.md)

  - [<span data-ttu-id="e2e02-115">Устранение неполадок подключаемого модуля VDI для Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2e02-115">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-the-lync-vdi-plug-in.md)

  - [<span data-ttu-id="e2e02-116">Поддерживаемые технологии виртуализации и известные ограничения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2e02-116">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>](lync-server-2013-supported-virtualization-technologies-and-known-limitations.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

