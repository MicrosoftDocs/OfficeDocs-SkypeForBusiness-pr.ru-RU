---
title: 'Lync Server 2013: развертывание корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b56065b0e3b7e7ef25c81f20140e8869dbe5376
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>Развертывание корпоративной голосовой связи в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-03_

Lync Server 2013, Корпоративная голосовая связь входит в состав инфраструктуры Lync Server 2013.

Для развертывания Корпоративной голосовой связи необходимо выполнить следующие действия.

<div id="sectionSection0" class="section">

1.  Ознакомьтесь с разделом [планирование для корпоративной голосовой связи в Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) документации по планированию.

2.  Подготовьте планы по функциям и компонентам, развертываемым с этой рабочей нагрузкой.

3.  Запустите средство планирования, чтобы создать топологию, отражающую ваши решения по развертыванию.

4.  Откройте проект топологии в построителе топологий, как описано в статье [Определение и Настройка топологии в Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md) в документации по развертыванию.
    
    <div>
    

    > [!NOTE]  
    > Установка построителя топологии является частью процесса развертывания внутреннего пула. Дополнительные сведения см. в <A href="lync-server-2013-install-lync-server-administrative-tools.md">статье Установка средств администрирования Lync Server 2013</A> в документации по развертыванию.

    
    </div>

Кроме того, вы должны уже развернуть Lync Server Enterprise Edition на центральных сайтах и сайтах филиалов, которые соответствуют эталонной топологии, которую вы выбираете для развертывания. Компоненты корпоративной голосовой связи невозможно развернуть, пока не будут определены, опубликованы и установлены файлы по крайней мере для одного внутреннего пула, и для определения и публикации внутреннего пула необходимо использовать построитель топологий.

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

Для просмотра эталонных топологий с примерами того, где могут развертываться роли сервера корпоративной голосовой связи (и их связи друг с другом и другими ролями сервера Lync Server 2013), ознакомьтесь с [эталонными топологиями в Lync server 2013](lync-server-2013-reference-topologies.md) в документации по планированию.

Чтобы просмотреть эталонную топологию, в которой описывается пример развертывания контроля допуска звонков, включая области сети, сетевые сайты и подсети, смотрите [Пример: сбор требований для контроля допуска звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) в документации по планированию.

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> Чтобы развернуть корпоративную голосовую связь на центральном сайте, продолжайте чтение разделов, приведенных в этом разделе. Чтобы развернуть корпоративную голосовую связь на сайте филиала, перейдите к разделу <A href="lync-server-2013-deploying-branch-sites.md">Развертывание сайтов филиалов в Lync Server 2013</A> в документации по развертыванию.



</div>

В этом разделе описываются варианты развертывания с размещением сервера-посредника на каждом сервере переднего плана или сервере Standard Edition (рекомендуется), а также варианты развертывания отдельного пула cерверов-посредников.

Вы можете пропустить следующее содержимое, если вы использовали построитель топологий для определения и публикации топологии, которая размещает сервер-посредник на каждом сервере переднего плана или сервере Standard Edition, так как мастер развертывания уже установил файлы для Сервер-посредник при установке файлов для пула серверов переднего плана или сервера Standard Edition:

  - [Настройка магистральных линий в Lync Server 2013](lync-server-2013-configuring-trunks.md)

Если вы использовали построитель топологий для определения и публикации сервера-посредника в автономном пуле, можно использовать следующее содержимое:

  - Убедитесь, что ваша топология соответствует требованиям к программному обеспечению и среде, как описано в статье [Предварительные требования к корпоративной голосовой связи для Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md).

</div>

<div>

## <a name="in-this-section"></a>Содержание

  - <span></span>  
    [Требования к корпоративной голосовой связи для Lync Server 2013](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [Развертывание серверов-посредников и определение одноранговых узлов в Lync Server 2013](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [Настройка магистральных линий в Lync Server 2013](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [Настройка абонентских планов в Lync Server 2013](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [Настройка политик голосовой связи, записей использования PSTN и маршрутов голосовой связи в Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [Экспорт и импорт конфигурации маршрутизации голосовой связи в Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [Проверка маршрутизации голосовой связи в Lync Server 2013](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [Развертывание локальной единой системы обмена сообщениями Exchange для предоставления голосовой почты Lync Server 2013](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [Предоставление пользователям Lync Server 2013 голосовой почты в размещенной единой системе обмена сообщениями Exchange](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [Настройка локальной интеграции Lync Server 2013 с Exchange Online](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [Развертывание расширенных функций корпоративной голосовой связи в Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [Сведения о регионах сети, сайтах и подсетях в Lync Server 2013](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Создание или изменение области сети в Lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Создание или изменение сетевого сайта в Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Связывание подсети с сетевым сайтом в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Настройка контроля допуска звонков в Lync Server 2013](lync-server-2013-configure-call-admission-control.md)
    
      - [Настройка расширенного 9-1-1 в Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Настройка обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [Разрешить пользователям использовать корпоративную голосовую связь в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Развертывание сайтов филиалов в Lync Server 2013](lync-server-2013-deploying-branch-sites.md)  
[Настройка конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)  
[Настройка парковки вызовов в Lync Server 2013](lync-server-2013-configuring-call-park.md)  
[Настройка объявлений для неназначенных номеров в Lync Server 2013](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Развертывание мониторинга в Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

