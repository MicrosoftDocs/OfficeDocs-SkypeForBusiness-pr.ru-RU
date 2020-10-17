---
title: 'Lync Server 2013: требования Lync для Android'
description: 'Lync Server 2013: требования Lync для Android.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync for Android requirements
ms:assetid: 4ff53e03-0c1f-4a2b-9cec-1131c2a48563
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690980(v=OCS.15)
ms:contentKeyID: 53312965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d3d3aa6e428c3a73f1b9263fe9cf13e5aa9fff0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570475"
---
# <a name="lync-for-android-requirements-in-lync-server-2013"></a><span data-ttu-id="f44de-103">Требования Lync для Android в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f44de-103">Lync for Android requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f44de-104">_**Последнее изменение темы:** 2014-04-24_</span><span class="sxs-lookup"><span data-stu-id="f44de-104">_**Topic Last Modified:** 2014-04-24_</span></span>

<span data-ttu-id="f44de-105">Microsoft Lync 2013 Microsoft Lync 2013 для Android предоставляет возможности обмена мгновенными сообщениями, расширенное присутствие и возможности присоединения к собранию Lync для пользователей в вашей организации, подключающихся с устройства с Android.</span><span class="sxs-lookup"><span data-stu-id="f44de-105">Microsoft Lync 2013 Microsoft Lync 2013 for Android provides instant messaging (IM), enhanced presence, and Lync meeting join capabilities for users in your organization who are connecting from an Android device.</span></span> <span data-ttu-id="f44de-106">В этом разделе описываются вопросы, касающиеся Lync 2013 для Android, в том числе предварительные требования, технические требования и необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="f44de-106">This topic describes considerations for Lync 2013 for Android, including prerequisites, technical requirements, and required components.</span></span>

<div>

## <a name="lync-for-android-prerequisite"></a><span data-ttu-id="f44de-107">Lync для предварительных требований для Android</span><span class="sxs-lookup"><span data-stu-id="f44de-107">Lync for Android Prerequisite</span></span>

<span data-ttu-id="f44de-108">Для поддержки Lync 2013 для Android устройство Android должно удовлетворять следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="f44de-108">To support Lync 2013 for Android, the Android device must meet the following requirements:</span></span>

  - <span data-ttu-id="f44de-109">Устройство с Android должно работать под управлением Android 4,0 или более поздней телефонной или планшетной операционной системы, в том числе планшетов, за исключением тех, которые имеют микросхемы Tegra2.</span><span class="sxs-lookup"><span data-stu-id="f44de-109">The Android device must be running Android 4.0 or a later phone- or tablet-oriented operating system, including tablets, except those with the Tegra2 chip.</span></span>

  - <span data-ttu-id="f44de-110">На устройстве должно быть Двухъядерный или более мощный процессор с тактовой частотой 1,2 ГГц.</span><span class="sxs-lookup"><span data-stu-id="f44de-110">The device must have a 1.2 GHz dual core or higher CPU.</span></span>

  - <span data-ttu-id="f44de-111">Разрешение камеры устройства (передняя/задняя) должна быть VGA или выше.</span><span class="sxs-lookup"><span data-stu-id="f44de-111">The device camera (front/rear) resolution should be VGA or higher.</span></span>

  - <span data-ttu-id="f44de-112">Другие требования к оборудованию должны быть выровнены с помощью документа с определением совместимости для Android 4,0.</span><span class="sxs-lookup"><span data-stu-id="f44de-112">Other hardware requirements should be aligned with Android 4.0 Compatibility Definition Document.</span></span>

</div>

<div>

## <a name="other-technical-considerations"></a><span data-ttu-id="f44de-113">Другие технические вопросы</span><span class="sxs-lookup"><span data-stu-id="f44de-113">Other Technical Considerations</span></span>

<span data-ttu-id="f44de-114">На платформе устройства с Android приложение Lync может работать в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="f44de-114">On the Android device platform, the Lync application can run in the background.</span></span> <span data-ttu-id="f44de-115">Таким образом, в отличие от других платформ мобильных устройств, Push-уведомления не требуются для устройств с Android.</span><span class="sxs-lookup"><span data-stu-id="f44de-115">Therefore, unlike other mobile device platforms, push notifications are not required for Android devices.</span></span> <span data-ttu-id="f44de-116">Единственный способ выйти из приложения Lync на устройстве с Android заключается в явном выходе из Lync.</span><span class="sxs-lookup"><span data-stu-id="f44de-116">The only way to exit the Lync application on an Android device is to explicitly sign out of Lync.</span></span> <span data-ttu-id="f44de-117">Эта версия приложения Lync не поддерживается на устройствах с наборами микросхем Тегра 2.</span><span class="sxs-lookup"><span data-stu-id="f44de-117">This version of the Lync application is not supported on devices with Tegra 2 chipsets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

