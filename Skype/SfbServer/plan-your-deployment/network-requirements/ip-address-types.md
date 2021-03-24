---
title: Настройка типов IP-адресов в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: Сводка. Просмотрите ниже соображения типа IP-адресов перед реализацией Skype для бизнеса Server.
ms.openlocfilehash: ba10dd223e7e099d27e31bddce478603f50e49a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101255"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="06c62-103">Настройка типов IP-адресов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="06c62-103">Configure IP address types in Skype for Business</span></span>

<span data-ttu-id="06c62-104">**Сводка:** Просмотрите ниже соображения типа IP-адресов перед реализацией Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="06c62-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>

<span data-ttu-id="06c62-105">Развертывание типов IP-адресов с помощью параметров топологии, настроенных в Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="06c62-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="06c62-106">В этом разделе описывается развертывание типов IP-адресов на серверах переднего типа, серверах-посредниках и edge Servers.</span><span class="sxs-lookup"><span data-stu-id="06c62-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>

## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="06c62-107">Развертывание типов IP-адресов на переднем сервере</span><span class="sxs-lookup"><span data-stu-id="06c62-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="06c62-108">Используя Topology Builder, выполните действия в следующей процедуре для развертывания типов IP-адресов на переднем сервере.</span><span class="sxs-lookup"><span data-stu-id="06c62-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="06c62-109">Развертывание типов IP-адресов на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="06c62-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="06c62-p102">В узле **Enterprise Edition Front End pools** (Интерфейсные пулы Enterprise Edition) щелкните правой кнопкой мыши сервер пула и затем выберите команду **Edit Properties** (Изменить свойства). (Либо выберите сервер и затем в меню **Action** (Действие) выберите команду **Edit Properties** (Изменить свойства).)</span><span class="sxs-lookup"><span data-stu-id="06c62-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="06c62-112">В диалоговом окне **Edit Properties** (Изменение свойств) выберите тип IP-адреса, который необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="06c62-112">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="06c62-113">Для конфигурации с двойным стеком выберите **Включить IPv4** и **включить IPv6.**</span><span class="sxs-lookup"><span data-stu-id="06c62-113">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**.</span></span>

   <span data-ttu-id="06c62-114">**Диалоговое окно Edit Properties (Изменение свойств) для пула серверов переднего плана**</span><span class="sxs-lookup"><span data-stu-id="06c62-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

   - <span data-ttu-id="06c62-p104">**Use all configured IP addresses** (Использовать все заданные IP-адреса). Выберите этот параметр, если требуется разрешить использование любых IP-адресов, заданных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="06c62-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

     > [!NOTE]
     > <span data-ttu-id="06c62-117">Этот параметр рекомендуется использовать для конфигураций IP версии 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="06c62-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

   - <span data-ttu-id="06c62-p105">**Limit service usage to selected IP addresses** (Разрешить использовать службу только указанным IP-адресам). Выберите этот параметр, чтобы указать адрес, используемый на новом сервере. Если вы выберете этот параметр, потребуется ввести значение в поле **Primary IP address** (Основной IP-адрес).</span><span class="sxs-lookup"><span data-stu-id="06c62-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>

   - <span data-ttu-id="06c62-p106">**Primary IP address** (Основной IP-адрес). Введите IP-адрес, который будет использовать сервер для всех коммуникаций, за исключением ТСОП. Введенный IP-адрес должен соответствовать формату выбранного типа адресов.</span><span class="sxs-lookup"><span data-stu-id="06c62-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

   - <span data-ttu-id="06c62-p107">**PSTN IP address** (IP-адрес ТСОП). Укажите IP-адрес ТСОП, используемый при расположении сервера-посредника на сервере переднего плана. Введенный IP-адрес должен соответствовать формату выбранного типа адресов.</span><span class="sxs-lookup"><span data-stu-id="06c62-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>

> [!NOTE]
> <span data-ttu-id="06c62-127">Установка дополнительных карт сетевого интерфейса (NICs) для поддержки конфигурации IP-адресов PSTN (или по любой другой причине) на интерфейсных серверах не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="06c62-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration (or for any other reason) on Front End Servers is not supported.</span></span> <span data-ttu-id="06c62-128">Дополнительные сведения о поддерживаемых конфигурациях NIC для Skype для бизнеса Server см. в дополнительных сведениях о аппаратных платформах [Server для Lync Server 2013.](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms)</span><span class="sxs-lookup"><span data-stu-id="06c62-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-server-hardware-platforms).</span></span>

## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="06c62-129">Развертывание типов IP-адресов на сервере-посреднике</span><span class="sxs-lookup"><span data-stu-id="06c62-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="06c62-130">Используя Topology Builder, выполните действия в следующей процедуре для развертывания типов IP-адресов на сервере-посреднике.</span><span class="sxs-lookup"><span data-stu-id="06c62-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="06c62-131">Развертывание типов IP-адресов на сервере-посреднике</span><span class="sxs-lookup"><span data-stu-id="06c62-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="06c62-132">В Topology Builder в **пулах посредников** щелкните правой кнопкой мыши сервер в пуле, а затем выберите **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="06c62-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="06c62-133">(Либо выберите сервер и затем в меню **Action** (Действие) выберите команду **Edit Properties** (Изменить свойства).)</span><span class="sxs-lookup"><span data-stu-id="06c62-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

- <span data-ttu-id="06c62-p110">В диалоговом окне **Edit Properties** (Изменение свойств) выберите тип IP-адреса, который необходимо настроить. Для конфигурации двойного стека установите флажки **Enable IPv4** (Включить IP версии 4) и **Enable IPv6** (Включить IP версии 6).</span><span class="sxs-lookup"><span data-stu-id="06c62-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>

   <span data-ttu-id="06c62-136">**Диалоговое окно "Изменение свойств" для пула сервера-посредника**</span><span class="sxs-lookup"><span data-stu-id="06c62-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="06c62-p111">**Use all configured IP addresses** (Использовать все заданные IP-адреса). Выберите этот параметр, если требуется разрешить использование любых IP-адресов, заданных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="06c62-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

    > [!NOTE]
    > <span data-ttu-id="06c62-139">Это рекомендуемый параметр для конфигураций с IP версии 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="06c62-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

  - <span data-ttu-id="06c62-p112">**Ограничить использование службы для выбранных IP-адресов**. Выберите этот параметр, чтобы указать конкретный адрес, который будет использоваться на новом сервере. Если выбран данный параметр, необходимо ввести значения для основного IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="06c62-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>

  - <span data-ttu-id="06c62-p113">**Основной IP-адрес**. Введите IP-адрес, который сервер будет использовать для всех коммуникаций, кроме ТСОП. Введенный IP-адрес должен соответствовать формату выбранного типа адреса.</span><span class="sxs-lookup"><span data-stu-id="06c62-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

  - <span data-ttu-id="06c62-p114">**PSTN IP address** (IP-адрес ТСОП). Укажите IP-адрес ТСОП, используемый при расположении сервера-посредника на сервере переднего плана. Введенный IP-адрес должен соответствовать формату выбранного типа адресов.</span><span class="sxs-lookup"><span data-stu-id="06c62-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="06c62-149">Мы поддерживаем только две сетевые карты на *выделенных* серверах-посредниках.</span><span class="sxs-lookup"><span data-stu-id="06c62-149">We only support two network cards on *dedicated* Mediation Servers.</span></span> <span data-ttu-id="06c62-150">Если роль посредника Sserver расположена в переднем конце, то двойные сетевые карты не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="06c62-150">If the Mediation Sserver role is collocated on the Front End, then dual network cards are not supported.</span></span> 

> [!NOTE]
> - <span data-ttu-id="06c62-151">Дополнительные сведения о поддерживаемых конфигурациях NIC для Skype для бизнеса Server 2015 см. в см. в руб. [Оборудование для Skype для бизнеса Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="06c62-151">For more information about supported NIC configurations for Skype for Business Server 2015, see [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span></span>
> - <span data-ttu-id="06c62-152">Дополнительные сведения о поддерживаемых конфигурациях NIC для Skype для бизнеса Server 2019 см. в см. в руб. Оборудование [для Skype для бизнеса Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span><span class="sxs-lookup"><span data-stu-id="06c62-152">For more information about supported NIC configurations for Skype for Business Server 2019, see [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span></span>



## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="06c62-153">Развертывание типов IP-адресов на edge Server</span><span class="sxs-lookup"><span data-stu-id="06c62-153">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="06c62-154">Используя Topology Builder, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="06c62-154">Using Topology Builder, perform the following steps:</span></span>

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="06c62-155">Развертывание типов IP-адресов в пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="06c62-155">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="06c62-156">В Topology Builder в **пулах Edge** щелкните правой кнопкой мыши сервер в пуле, а затем выберите **Edit Properties**.</span><span class="sxs-lookup"><span data-stu-id="06c62-156">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="06c62-157">(можно также выбрать сервер, а затем выбрать пункт **Edit Properties (Изменить свойства)** в меню **Action (Действие)**.)</span><span class="sxs-lookup"><span data-stu-id="06c62-157">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="06c62-158">В окне **изменения свойств** выберите конфигурацию IP-адресов, которую планируется поддерживать.</span><span class="sxs-lookup"><span data-stu-id="06c62-158">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>

3. <span data-ttu-id="06c62-159">Для каждого выбранного типа адреса необходимо предоставить соответствующие внутренние и внешние адреса.</span><span class="sxs-lookup"><span data-stu-id="06c62-159">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>