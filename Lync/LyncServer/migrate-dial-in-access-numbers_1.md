---
title: Перенос номеров доступа
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
ms.openlocfilehash: a13fdf36dcd36dc71df8ffa06c273c2b2b0f0292
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="7e545-102">Перенос номеров доступа</span><span class="sxs-lookup"><span data-stu-id="7e545-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e545-103">_**Тема последнего изменения:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="7e545-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="7e545-104">Для миграции номеров доступа с телефонным подключением необходимо выполнить два действия: Запуск командлета **Import-кслегациконфигуратион** (выполнен ранее в разделе [политики импорта и параметры](import-policies-and-settings.md)) для миграции абонентов и других параметров номеров доступа для телефонного подключения, а также выполнение командлета **Move-ксаппликатионендпоинт** для миграции объектов контакта.</span><span class="sxs-lookup"><span data-stu-id="7e545-104">Migrating dial-in access numbers requires two steps: running the **Import-CsLegacyConfiguration** cmdlet (completed earlier in [Import policies and settings](import-policies-and-settings.md)) to migrate dial plans and other dial-in access number settings, and running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span>

<div>

## <a name="to-migrate-dial-in-access-numbers"></a><span data-ttu-id="7e545-105">Миграция номеров доступа для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="7e545-105">To migrate dial-in access numbers</span></span>

1.  <span data-ttu-id="7e545-106">Откройте средство администрирования Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7e545-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="7e545-107">В дереве консоли щелкните правой кнопкой мыши узел леса, выберите пункт **Свойства**, а затем — **свойства участника Конференц**-связи.</span><span class="sxs-lookup"><span data-stu-id="7e545-107">In the console tree, right-click the forest node, click **Properties**, and then click **Conferencing Attendant Properties**.</span></span>

3.  <span data-ttu-id="7e545-108">На вкладке **номера телефонов Access** выберите **обслуживание по пулам** , чтобы отсортировать номера телефонов Access по связанному пулу, и определите все номера доступа для пула, из которого выполняется миграция.</span><span class="sxs-lookup"><span data-stu-id="7e545-108">On the **Access Phone Numbers** tab, click **Serviced by Pool** to sort the access phone numbers by their associated pool, and identify all the access numbers for the pool from which you are migrating.</span></span>

4.  <span data-ttu-id="7e545-109">Чтобы определить URI SIP для каждого номера доступа, дважды щелкните номер доступа, чтобы открыть диалоговое окно **изменить номер участника конференции** , и просмотрите раздел **URI SIP**.</span><span class="sxs-lookup"><span data-stu-id="7e545-109">To identify the SIP URI for each access number, double-click the access number to open the **Edit Conferencing Attendant Number** dialog box, and look under **SIP URI**.</span></span>

5.  <span data-ttu-id="7e545-110">Откройте командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7e545-110">Open the Lync Server Management Shell.</span></span>

6.  <span data-ttu-id="7e545-111">Чтобы переместить каждый номер доступа с телефонным подключением в пул, размещенный на Lync Server 2013, выполните команду:</span><span class="sxs-lookup"><span data-stu-id="7e545-111">To move each dial-in access number to a pool hosted on Lync Server 2013, run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  <span data-ttu-id="7e545-112">В средстве администрирования Office Communications Server 2007 R2 на вкладке **номера телефонов Access** убедитесь в том, что для пула Office Communications Server 2007 R2, из которого выполняется миграция, нет номеров доступа с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="7e545-112">In the Office Communications Server 2007 R2 Administrative tool, on the **Access Phone Numbers** tab, verify that no dial-in access numbers remain for the Office Communications Server 2007 R2 pool from which you are migrating.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

