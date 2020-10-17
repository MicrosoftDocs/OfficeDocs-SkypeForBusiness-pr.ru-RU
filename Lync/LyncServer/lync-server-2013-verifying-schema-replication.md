---
title: 'Lync Server 2013: проверка репликации схемы'
description: 'Lync Server 2013: проверка репликации схемы.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 019cd06db05a9ba683767f550a712ef188b47508
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560175"
---
# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a><span data-ttu-id="6f129-103">Проверка репликации схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f129-103">Verifying Active Directory schema replication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f129-104">_**Последнее изменение темы:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="6f129-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="6f129-105">Прежде чем перейти к подготовке леса, вручную проверьте, был ли реплицирован раздел схемы.</span><span class="sxs-lookup"><span data-stu-id="6f129-105">Before you run forest preparation, manually verify that the schema partition has been replicated.</span></span>

<div>

## <a name="to-manually-verify-schema-replication"></a><span data-ttu-id="6f129-106">Проверка репликации схемы вручную</span><span class="sxs-lookup"><span data-stu-id="6f129-106">To manually verify schema replication</span></span>

1.  <span data-ttu-id="6f129-107">Выполните вход на контроллер домена с учетной записью члена группы "Администраторы предприятия".</span><span class="sxs-lookup"><span data-stu-id="6f129-107">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="6f129-108">Чтобы открыть редактор ADSI, нажмите кнопку **Пуск**, выберите **Администрирование** и затем выберите **Редактирование ADSI**.</span><span class="sxs-lookup"><span data-stu-id="6f129-108">Open ADSI Edit by clicking **Start**, clicking **Administrative Tools**, and then clicking **ADSI Edit**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="6f129-109">Для открытия редактора также можно запустить оснастку <STRONG>adsiedit.msc</STRONG> в командной строке.</span><span class="sxs-lookup"><span data-stu-id="6f129-109">Alternatively, you can run <STRONG>adsiedit.msc</STRONG> from the command line.</span></span>

    
    </div>

3.  <span data-ttu-id="6f129-110">В дереве консоли управления (MMC) выберите **Редактирование ADSI**.</span><span class="sxs-lookup"><span data-stu-id="6f129-110">In the Microsoft Management Console (MMC) tree, if it is not already selected, click **ADSI Edit**.</span></span>

4.  <span data-ttu-id="6f129-111">В меню **Действие**щелкните **Подключиться к**.</span><span class="sxs-lookup"><span data-stu-id="6f129-111">On the **Action** menu, click **Connect to**.</span></span>

5.  <span data-ttu-id="6f129-112">В диалоговом окне **Параметры подключения** выберите **Схема** в раскрывающемся списке **Выберите известный контекст именования** и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="6f129-112">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>

6.  <span data-ttu-id="6f129-113">В контейнере схемы выполните поиск объекта CN=ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="6f129-113">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="6f129-114">Если объект существует, атрибут **rangeUpper** имеет значение 1150, а атрибут **rangeLower** — значение 3, то схема была успешно обновлена и реплицирована.</span><span class="sxs-lookup"><span data-stu-id="6f129-114">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="6f129-115">Если этот объект не существует или значения атрибутов **rangeUpper** и **rangeLower** отличаются от указанных выше, то обновление и репликация схемы не выполнены.</span><span class="sxs-lookup"><span data-stu-id="6f129-115">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6f129-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6f129-116">See Also</span></span>


[<span data-ttu-id="6f129-117">Выполнение подготовки схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f129-117">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)  


[<span data-ttu-id="6f129-118">Подготовка схемы Active Directory в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f129-118">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

