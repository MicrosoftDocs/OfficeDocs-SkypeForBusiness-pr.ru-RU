---
title: 'Lync Server 2013: Настройка хранилища файлов DFS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8400d62560b1b599a7763f8582fd21da23e6948f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>Настройка хранилища файлов DFS для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-05-23_

Lync Server 2013 поддерживает использование файловых ресурсов распределенной файловой системы (DFS). Подробнее о DFS для Windows Server 2008 вы найдете в статье Пошаговое руководство по работе с DFS для Windows Server 2008 [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835)по адресу. Чтобы использовать DFS, Lync Server 2013 требует наличия следующих компонентов:

  - Пространства имен являются доменными.

  - Все серверы пространств имен работают под управлением Windows 2008 или более поздней версии.

Для установки Lync Server 2013 необходимо, чтобы разрешения для общей папки разрешают полный доступ к администратору. В этом случае Lync Server 2013 будет использовать разрешения NTFS для папок списка управления доступом. Унаследованные разрешения для общих папок DFS не будут использоваться для ограничения доступа.

Дополнительные сведения о требованиях к общему файловому ресурсу приведены [в статье поддержка хранения файлов в Lync Server 2013](lync-server-2013-file-storage-support.md) в документации по поддержке.

<div>


> [!NOTE]  
> Возможно, вы ищете сведения о настройке общего ресурса, не относящегося к DFS. Если это так, проверьте <A href="lync-server-2013-hardware-setup.md">настройку аппаратного обеспечения для Lync Server 2013</A>.



</div>

Ниже описывается, как правильно настроить разрешения для общих папок с помощью мастера пространств имен DFS (как описано в руководстве по настройке DFS).

<div>

## <a name="to-configure-shared-folder-permissions"></a>Настройка разрешений для общих папок

1.  В меню **Пуск** последовательно выберите пункты **Все программы**, **Администрирование** и **Управление DFS**.

2.  В дереве консоли оснастки "Управление DFS" щелкните правой кнопкой мыши сервер пространства имен (например, filesrv1.contoso.com) и выберите пункт **Изменить параметры**.

3.  Выберите пункт **Разрешения для общей папки**.

4.  Выберите пункт **Использовать пользовательские разрешения**.

5.  Для группы администраторов выберите в разделе **Разрешить** следующие пункты:
    
      - **Полный доступ**
    
      - **Изменение**
    
      - **Чтение**

6.  Нажмите кнопку **Применить**, а затем кнопку **ОК**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

