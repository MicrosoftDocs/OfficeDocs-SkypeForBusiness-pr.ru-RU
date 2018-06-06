---
title: Настройка типов IP-адресов в Skype для бизнеса
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/22/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 'Сводка: Обзор рекомендаций типа IP-адрес ниже перед реализацией Скайп для Business Server 2015.'
ms.openlocfilehash: adebab15a0c10310b25af30f6e933625df61dc3d
ms.sourcegitcommit: a612ebe25e06c2cb090f776325712caf3cf3b943
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2018
ms.locfileid: "19630149"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="5f360-103">Настройка типов IP-адресов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5f360-103">Configure IP address types in Skype for Business</span></span>
 
<span data-ttu-id="5f360-104">**Сводка:** Обзор рекомендаций типа IP-адрес ниже перед реализацией Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5f360-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5f360-105">Развертывание типов IP-адресов с помощью параметров топологии, которые можно настроить в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="5f360-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="5f360-106">В этом разделе описывается развертывание типов IP-адресов на серверах переднего плана, серверы-посредники и пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="5f360-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>
  
## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="5f360-107">Развертывание типов IP-адресов на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="5f360-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="5f360-108">С помощью построителя топологий, выполните действия, описанные в следующей процедуры для развертывание типов IP-адресов на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="5f360-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>
  
### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="5f360-109">Развертывание типов IP-адресов на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="5f360-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="5f360-p102">В узле **Enterprise Edition Front End pools** (Интерфейсные пулы Enterprise Edition) щелкните правой кнопкой мыши сервер пула и затем выберите команду **Edit Properties** (Изменить свойства). (Либо выберите сервер и затем в меню **Action** (Действие) выберите команду **Edit Properties** (Изменить свойства).)</span><span class="sxs-lookup"><span data-stu-id="5f360-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
2. <span data-ttu-id="5f360-p103">В диалоговом окне **Edit Properties** (Изменение свойств) выберите тип IP-адреса, который необходимо настроить. Для конфигурации двойного стека установите флажки **Enable IPv4** (Включить IP версии 4) и **Enable IPv6** (Включить IP версии 6), как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="5f360-p103">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
   <span data-ttu-id="5f360-114">**Изменение свойства для пула сервера переднего плана**</span><span class="sxs-lookup"><span data-stu-id="5f360-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

  - <span data-ttu-id="5f360-p104">**Use all configured IP addresses** (Использовать все заданные IP-адреса). Выберите этот параметр, если требуется разрешить использование любых IP-адресов, заданных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f360-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5f360-117">Этот параметр рекомендуется использовать для конфигураций IP версии 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="5f360-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span> 
  
  - <span data-ttu-id="5f360-p105">**Limit service usage to selected IP addresses** (Разрешить использовать службу только указанным IP-адресам). Выберите этот параметр, чтобы указать адрес, используемый на новом сервере. Если вы выберете этот параметр, потребуется ввести значение в поле **Primary IP address** (Основной IP-адрес).</span><span class="sxs-lookup"><span data-stu-id="5f360-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>
    
  - <span data-ttu-id="5f360-p106">**Primary IP address** (Основной IP-адрес). Введите IP-адрес, который будет использовать сервер для всех коммуникаций, за исключением ТСОП. Введенный IP-адрес должен соответствовать формату выбранного типа адресов.</span><span class="sxs-lookup"><span data-stu-id="5f360-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
  - <span data-ttu-id="5f360-p107">**PSTN IP address** (IP-адрес ТСОП). Укажите IP-адрес ТСОП, используемый при расположении сервера-посредника на сервере переднего плана. Введенный IP-адрес должен соответствовать формату выбранного типа адресов.</span><span class="sxs-lookup"><span data-stu-id="5f360-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5f360-127">Установка дополнительных сетевых карт (сетевых адаптеров) для поддержки ТСОП IP-адрес на серверах переднего плана не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5f360-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration on Front End Servers is not supported.</span></span> <span data-ttu-id="5f360-128">Дополнительные сведения о поддерживаемых конфигурациях сетевой Адаптер для Скайп для Business Server можно [аппаратные серверные платформы для Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span><span class="sxs-lookup"><span data-stu-id="5f360-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span> 
  
## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="5f360-129">Развертывание типов IP-адресов на сервере-посреднике</span><span class="sxs-lookup"><span data-stu-id="5f360-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="5f360-130">С помощью построителя топологий, выполните действия, описанные в следующей процедуры для развертывание типов IP-адресов на сервере-посреднике.</span><span class="sxs-lookup"><span data-stu-id="5f360-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>
  
### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="5f360-131">Развертывание типов IP-адресов на сервере-посреднике</span><span class="sxs-lookup"><span data-stu-id="5f360-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="5f360-132">В построителе топологий, в разделе **Пулы-посредники**щелкните правой кнопкой мыши сервер в пуле и затем выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5f360-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="5f360-133">(Или же выберите сервер и щелкните **Edit Properties** (Изменить свойства) в меню **Action** (Действие).)</span><span class="sxs-lookup"><span data-stu-id="5f360-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
- <span data-ttu-id="5f360-p110">В диалоговом окне **Edit Properties** (Изменение свойств) выберите тип IP-адреса, который необходимо настроить. Для конфигурации двойного стека установите флажки **Enable IPv4** (Включить IP версии 4) и **Enable IPv6** (Включить IP версии 6), как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="5f360-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
   <span data-ttu-id="5f360-136">**Изменение свойства для пула серверов-посредников**</span><span class="sxs-lookup"><span data-stu-id="5f360-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="5f360-p111">**Use all configured IP addresses** (Использовать все заданные IP-адреса). Выберите этот параметр, если требуется разрешить использование любых IP-адресов, заданных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="5f360-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5f360-139">Этот параметр рекомендуется использовать для конфигураций IP версии 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="5f360-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span> 
  
  - <span data-ttu-id="5f360-p112">**Limit service usage to selected IP addresses** (Разрешить использовать службу только указанным IP-адресам). Выберите этот параметр, чтобы указать адрес, используемый на новом сервере. Если вы выберете этот параметр, потребуется ввести значение в поле Primary IP address (Основной IP-адрес).</span><span class="sxs-lookup"><span data-stu-id="5f360-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>
    
  - <span data-ttu-id="5f360-p113">**Primary IP address** (Основной IP-адрес). Введите IP-адрес, который будет использовать сервер для всех коммуникаций, за исключением ТСОП. Введенный IP-адрес должен соответствовать формату выбранного типа адресов.</span><span class="sxs-lookup"><span data-stu-id="5f360-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
  - <span data-ttu-id="5f360-p114">**PSTN IP address** (IP-адрес ТСОП). Укажите IP-адрес ТСОП, используемый при расположении сервера-посредника на сервере переднего плана. Введенный IP-адрес должен соответствовать формату выбранного типа адресов.</span><span class="sxs-lookup"><span data-stu-id="5f360-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5f360-149">Установка дополнительных сетевых адаптеров для поддержки ТСОП IP-адрес на изолированных серверах посредника не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5f360-149">The installation of additional NICs to support the PSTN IP address configuration on stand-alone Mediation Servers is not supported.</span></span> <span data-ttu-id="5f360-150">Дополнительные сведения о поддерживаемых конфигурациях сетевой Адаптер для Скайп для Business Server можно [аппаратные серверные платформы для Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span><span class="sxs-lookup"><span data-stu-id="5f360-150">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span> 
  
## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="5f360-151">Развертывание типов IP-адресов на пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="5f360-151">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="5f360-152">С помощью построителя топологий, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5f360-152">Using Topology Builder, perform the following steps:</span></span>
  
### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="5f360-153">Развертывание типов IP-адресов в пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="5f360-153">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="5f360-154">В построителе топологий, в разделе **пограничные пулы**щелкните правой кнопкой мыши сервер в пуле и затем выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="5f360-154">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="5f360-155">(Можно также выбрать сервер, а затем выбрать пункт **Edit Properties** (Изменить свойства) в меню **Action** (Действие).)</span><span class="sxs-lookup"><span data-stu-id="5f360-155">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>
    
2. <span data-ttu-id="5f360-156">В окне **изменения свойств** выберите конфигурацию IP-адресов, которую планируется поддерживать.</span><span class="sxs-lookup"><span data-stu-id="5f360-156">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>    

3. <span data-ttu-id="5f360-157">Для каждого выбранного типа адреса необходимо предоставить соответствующие внутренние и внешние адреса.</span><span class="sxs-lookup"><span data-stu-id="5f360-157">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
    