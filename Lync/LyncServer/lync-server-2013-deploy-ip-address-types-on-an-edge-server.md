---
title: 'Lync Server 2013: развертывание типов IP-адресов на пограничном сервере'
description: 'Lync Server 2013: развертывание типов IP-адресов на пограничном сервере.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7798ca2f7b38865a2b4ea373546dd4e7203f5b8e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558665"
---
# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a>Развертывание типов IP-адресов на пограничном сервере для Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-14_

С помощью построителя топологий выполните действия, описанные в следующей процедуре, для развертывания типов IP-адресов на пограничном сервере.

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a>Развертывание типов IP-адресов в пограничном сервере

1.  В построителе топологий в разделе **пограничные пулы**щелкните правой кнопкой мыши сервер в пуле, а затем выберите команду **изменить свойства**. (можно также выбрать сервер, а затем выбрать пункт **Edit Properties (Изменить свойства)** в меню **Action (Действие)**.)

2.  В окне **изменения свойств** выберите конфигурацию IP-адресов, которую планируется поддерживать. На следующих рисунках показана конфигурация двойного стека для внутреннего и внешнего интерфейса.
    
    **Внутренний интерфейс пограничного сервера с конфигурацией двойного стека**
    
    ![Страница общих свойств Lync Server](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Страница общих свойств Lync Server")
    
    **Внешний интерфейс пограничного сервера с конфигурацией двойного стека**
    
    ![Страница следующего прыжка или внешней конфигурации Lync Server](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Страница следующего прыжка или внешней конфигурации Lync Server")

3.  Для каждого выбранного типа адреса необходимо предоставить соответствующие внутренние и внешние адреса.

</div>

</div>

<span> </span>

</div>

</div>

</div>

