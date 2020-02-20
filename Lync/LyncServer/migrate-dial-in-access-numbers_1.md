---
title: Перенос номеров доступа для телефонного подключения
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fcc5b7dac5c9769d92afc86e7036f7e410f2278
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="c37da-102">Перенос номеров доступа для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="c37da-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c37da-103">_**Последнее изменение темы:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="c37da-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="c37da-104">Для переноса номеров доступа с телефонным подключением необходимо выполнить два действия: Запуск командлета **Import-CsLegacyConfiguration** (завершенный ранее в разделе [Импорт политик и параметров](import-policies-and-settings.md)) для переноса абонентских группы и других параметров номеров доступа с телефонным подключением, а также выполнения командлета **Move-CsApplicationEndpoint** для переноса объектов Contact.</span><span class="sxs-lookup"><span data-stu-id="c37da-104">Migrating dial-in access numbers requires two steps: running the **Import-CsLegacyConfiguration** cmdlet (completed earlier in [Import policies and settings](import-policies-and-settings.md)) to migrate dial plans and other dial-in access number settings, and running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span>

<div>

## <a name="to-migrate-dial-in-access-numbers"></a><span data-ttu-id="c37da-105">Чтобы мигрировать номера для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="c37da-105">To migrate dial-in access numbers</span></span>

1.  <span data-ttu-id="c37da-106">Откройте средство администрирования Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c37da-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="c37da-107">В дереве консоли щелкните правой кнопкой мыши узел леса, щелкните **Свойства**, затем щелкните **Свойства помощника по конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="c37da-107">In the console tree, right-click the forest node, click **Properties**, and then click **Conferencing Attendant Properties**.</span></span>

3.  <span data-ttu-id="c37da-108">На вкладке **Номера для телефонного подключения** щелкните **Обслуживается пулом** для упорядочивания номеров для телефонного подключения по соответствующим пулам и определите все номера для телефонного подключения в пуле, из которого будут перенесены эти номера.</span><span class="sxs-lookup"><span data-stu-id="c37da-108">On the **Access Phone Numbers** tab, click **Serviced by Pool** to sort the access phone numbers by their associated pool, and identify all the access numbers for the pool from which you are migrating.</span></span>

4.  <span data-ttu-id="c37da-109">Чтобы определить SIP URI для каждого номера доступа, дважды щелкните номер доступа, чтобы открыть диалоговое окно **Изменить номер помощника конференц-связи**, просмотрите раздел **SIP URI**.</span><span class="sxs-lookup"><span data-stu-id="c37da-109">To identify the SIP URI for each access number, double-click the access number to open the **Edit Conferencing Attendant Number** dialog box, and look under **SIP URI**.</span></span>

5.  <span data-ttu-id="c37da-110">Откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c37da-110">Open the Lync Server Management Shell.</span></span>

6.  <span data-ttu-id="c37da-111">Для перемещения каждого номера доступа с телефонным подключением в пул, размещенный на Lync Server 2013, выполните команду:</span><span class="sxs-lookup"><span data-stu-id="c37da-111">To move each dial-in access number to a pool hosted on Lync Server 2013, run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  <span data-ttu-id="c37da-112">В средстве администрирования Office Communications Server 2007 R2 на вкладке **номера телефонов для доступа** убедитесь, что в пуле Office communications Server 2007 R2 отсутствуют номера доступа для телефонного подключения, из которого выполняется миграция.</span><span class="sxs-lookup"><span data-stu-id="c37da-112">In the Office Communications Server 2007 R2 Administrative tool, on the **Access Phone Numbers** tab, verify that no dial-in access numbers remain for the Office Communications Server 2007 R2 pool from which you are migrating.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

