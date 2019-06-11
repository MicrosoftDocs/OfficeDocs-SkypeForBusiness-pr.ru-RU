---
title: 'Lync Server 2013: требования к Lync для Android'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync for Android requirements
ms:assetid: 4ff53e03-0c1f-4a2b-9cec-1131c2a48563
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690980(v=OCS.15)
ms:contentKeyID: 53312965
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb4c7ce56fb65b9f5998af90bfe63ab6eed5d28c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-for-android-requirements-in-lync-server-2013"></a><span data-ttu-id="bc639-102">Требования к Lync для Android в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc639-102">Lync for Android requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc639-103">_**Тема последнего изменения:** 2014-04-24_</span><span class="sxs-lookup"><span data-stu-id="bc639-103">_**Topic Last Modified:** 2014-04-24_</span></span>

<span data-ttu-id="bc639-104">Microsoft Lync 2013 Microsoft Lync 2013 для Android обеспечивает обмен мгновенными сообщениями, расширенные возможности присутствия и присоединение к собранию Lync для пользователей в вашей организации, которые подключаются с устройства Android.</span><span class="sxs-lookup"><span data-stu-id="bc639-104">Microsoft Lync 2013 Microsoft Lync 2013 for Android provides instant messaging (IM), enhanced presence, and Lync meeting join capabilities for users in your organization who are connecting from an Android device.</span></span> <span data-ttu-id="bc639-105">В этой статье описаны вопросы, касающиеся Lync 2013 для Android, в том числе необходимые требования, технические требования и необходимые компоненты.</span><span class="sxs-lookup"><span data-stu-id="bc639-105">This topic describes considerations for Lync 2013 for Android, including prerequisites, technical requirements, and required components.</span></span>

<div>

## <a name="lync-for-android-prerequisite"></a><span data-ttu-id="bc639-106">Предварительные требования Lync для Android</span><span class="sxs-lookup"><span data-stu-id="bc639-106">Lync for Android Prerequisite</span></span>

<span data-ttu-id="bc639-107">Для поддержки Lync 2013 для Android устройство Android должно удовлетворять следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="bc639-107">To support Lync 2013 for Android, the Android device must meet the following requirements:</span></span>

  - <span data-ttu-id="bc639-108">На устройстве с Android должно быть запущено приложение Android 4,0 или более поздней операционной системы, в том числе на планшетах, кроме тех, для которых используется микросхема Tegra2.</span><span class="sxs-lookup"><span data-stu-id="bc639-108">The Android device must be running Android 4.0 or a later phone- or tablet-oriented operating system, including tablets, except those with the Tegra2 chip.</span></span>

  - <span data-ttu-id="bc639-109">На устройстве должно быть установлен Двухъядерный процессор с тактовой частотой 1,2 ГГц или выше.</span><span class="sxs-lookup"><span data-stu-id="bc639-109">The device must have a 1.2 GHz dual core or higher CPU.</span></span>

  - <span data-ttu-id="bc639-110">Разрешение камеры устройства (переднего или заднего) должно быть VGA или выше.</span><span class="sxs-lookup"><span data-stu-id="bc639-110">The device camera (front/rear) resolution should be VGA or higher.</span></span>

  - <span data-ttu-id="bc639-111">Другие требования к оборудованию должны быть выровнены по документу с определением совместимости с Android 4,0.</span><span class="sxs-lookup"><span data-stu-id="bc639-111">Other hardware requirements should be aligned with Android 4.0 Compatibility Definition Document.</span></span>

</div>

<div>

## <a name="other-technical-considerations"></a><span data-ttu-id="bc639-112">Другие технические вопросы</span><span class="sxs-lookup"><span data-stu-id="bc639-112">Other Technical Considerations</span></span>

<span data-ttu-id="bc639-113">На платформе устройства с Android приложение Lync может работать в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="bc639-113">On the Android device platform, the Lync application can run in the background.</span></span> <span data-ttu-id="bc639-114">Таким образом, в отличие от других платформ мобильных устройств, Push-уведомления не требуются для устройств с Android.</span><span class="sxs-lookup"><span data-stu-id="bc639-114">Therefore, unlike other mobile device platforms, push notifications are not required for Android devices.</span></span> <span data-ttu-id="bc639-115">Единственный способ выйти из приложения Lync на устройстве Android — явно выйти из Lync.</span><span class="sxs-lookup"><span data-stu-id="bc639-115">The only way to exit the Lync application on an Android device is to explicitly sign out of Lync.</span></span> <span data-ttu-id="bc639-116">Эта версия приложения Lync не поддерживается на устройствах с наборами микросхем Tegra 2.</span><span class="sxs-lookup"><span data-stu-id="bc639-116">This version of the Lync application is not supported on devices with Tegra 2 chipsets.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

