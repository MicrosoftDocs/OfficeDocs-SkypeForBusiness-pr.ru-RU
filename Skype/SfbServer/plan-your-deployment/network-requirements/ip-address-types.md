---
title: Настройка типов IP-адресов в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Сводка: Ознакомьтесь с приведенными ниже сведениями о типе IP-адреса, прежде чем приступить к реализации Skype для бизнеса Server.'
ms.openlocfilehash: 74cb0738c7c6eb0518d8ab4ed4fae7db66921bfb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802119"
---
# <a name="configure-ip-address-types-in-skype-for-business"></a><span data-ttu-id="839e8-103">Настройка типов IP-адресов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="839e8-103">Configure IP address types in Skype for Business</span></span>

<span data-ttu-id="839e8-104">**Сводка:** Прежде чем приступить к внедрению Skype для бизнеса Server, ознакомьтесь с приведенными ниже разрешениями.</span><span class="sxs-lookup"><span data-stu-id="839e8-104">**Summary:** Review the IP Address type considerations below before implementing Skype for Business Server.</span></span>

<span data-ttu-id="839e8-105">Типы IP-адресов развертываются с помощью параметров топологии, которые вы настраиваете в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="839e8-105">You deploy IP address types by using topology settings that you configure in Topology Builder.</span></span> <span data-ttu-id="839e8-106">В этом разделе описано, как развертывать типы IP-адресов на серверах переднего плана, серверах-посредниках и пограничных серверах.</span><span class="sxs-lookup"><span data-stu-id="839e8-106">This section describes how to deploy IP address types on Front End Servers, Mediation Servers, and Edge Servers.</span></span>

## <a name="deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="839e8-107">Развертывание типов IP-адресов на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="839e8-107">Deploy IP address types on a Front End Server</span></span>

<span data-ttu-id="839e8-108">С помощью построителя топологии выполните действия, описанные в описанной ниже процедуре, чтобы развернуть типы IP-адресов на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="839e8-108">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="839e8-109">Развертывание типов IP-адресов на сервере переднего плана</span><span class="sxs-lookup"><span data-stu-id="839e8-109">To deploy IP address types on a Front End Server</span></span>

1. <span data-ttu-id="839e8-p102">В узле **Enterprise Edition Front End pools** (Интерфейсные пулы Enterprise Edition) щелкните правой кнопкой мыши сервер пула и затем выберите команду **Edit Properties** (Изменить свойства). (Либо выберите сервер и затем в меню **Action** (Действие) выберите команду **Edit Properties** (Изменить свойства).)</span><span class="sxs-lookup"><span data-stu-id="839e8-p102">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**. (Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="839e8-112">В диалоговом окне **Edit Properties** (Изменение свойств) выберите тип IP-адреса, который необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="839e8-112">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="839e8-113">Для конфигурации с двумя стеками выберите **включить IPv4** и **Включить IPv6**.</span><span class="sxs-lookup"><span data-stu-id="839e8-113">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**.</span></span>

   <span data-ttu-id="839e8-114">**Диалоговое окно "Изменение свойств" для пула серверов переднего плана**</span><span class="sxs-lookup"><span data-stu-id="839e8-114">**Edit Properties dialog box for the Front End Server pool**</span></span>

   - <span data-ttu-id="839e8-p104">**Use all configured IP addresses** (Использовать все заданные IP-адреса). Выберите этот параметр, если требуется разрешить использование любых IP-адресов, заданных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="839e8-p104">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

     > [!NOTE]
     > <span data-ttu-id="839e8-117">Этот параметр рекомендуется использовать для конфигураций IP версии 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="839e8-117">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

   - <span data-ttu-id="839e8-p105">**Limit service usage to selected IP addresses** (Разрешить использовать службу только указанным IP-адресам). Выберите этот параметр, чтобы указать адрес, используемый на новом сервере. Если вы выберете этот параметр, потребуется ввести значение в поле **Primary IP address** (Основной IP-адрес).</span><span class="sxs-lookup"><span data-stu-id="839e8-p105">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for **Primary IP address**.</span></span>

   - <span data-ttu-id="839e8-p106">**Primary IP address** (Основной IP-адрес). Введите IP-адрес, который будет использовать сервер для всех коммуникаций, за исключением ТСОП. Введенный IP-адрес должен соответствовать формату выбранного типа адресов.</span><span class="sxs-lookup"><span data-stu-id="839e8-p106">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

   - <span data-ttu-id="839e8-p107">**PSTN IP address** (IP-адрес ТСОП). Укажите IP-адрес ТСОП, используемый при расположении сервера-посредника на сервере переднего плана. Введенный IP-адрес должен соответствовать формату выбранного типа адресов.</span><span class="sxs-lookup"><span data-stu-id="839e8-p107">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>

> [!NOTE]
> <span data-ttu-id="839e8-127">Установка дополнительных сетевых интерфейсных карт (NIC) для поддержки конфигурации IP-адреса PSTN (или по другим причинам) на серверах переднего плана не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="839e8-127">The installation of additional network interface cards (NICs) to support the PSTN IP address configuration (or for any other reason) on Front End Servers is not supported.</span></span> <span data-ttu-id="839e8-128">Дополнительные сведения о конфигурациях сетевых адаптеров для сервера Skype для бизнеса Server можно найти в разделе [аппаратные платформы сервера для Lync server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span><span class="sxs-lookup"><span data-stu-id="839e8-128">For more information about supported NIC configurations for Skype for Business Server, see [Server hardware platforms for Lync Server 2013](https://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx).</span></span>

## <a name="deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="839e8-129">Развертывание типов IP-адресов на сервере-посреднике</span><span class="sxs-lookup"><span data-stu-id="839e8-129">Deploy IP address types on a Mediation Server</span></span>

<span data-ttu-id="839e8-130">С помощью построителя топологии выполните действия, описанные в следующей процедуре, чтобы развернуть типы IP-адресов на сервере обновлений.</span><span class="sxs-lookup"><span data-stu-id="839e8-130">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="839e8-131">Развертывание типов IP-адресов на сервере-посреднике</span><span class="sxs-lookup"><span data-stu-id="839e8-131">To deploy IP address types on a Mediation Server</span></span>

- <span data-ttu-id="839e8-132">В построителе топологии в разделе **Пулы исправлений**щелкните правой кнопкой мыши сервер в пуле и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="839e8-132">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="839e8-133">(Или же выберите сервер и щелкните **Edit Properties** (Изменить свойства) в меню **Action** (Действие).)</span><span class="sxs-lookup"><span data-stu-id="839e8-133">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

- <span data-ttu-id="839e8-p110">В диалоговом окне **Edit Properties** (Изменение свойств) выберите тип IP-адреса, который необходимо настроить. Для конфигурации двойного стека установите флажки **Enable IPv4** (Включить IP версии 4) и **Enable IPv6** (Включить IP версии 6), как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="839e8-p110">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>

   <span data-ttu-id="839e8-136">**Диалоговое окно "Изменение свойств" для пула сервера-посредника**</span><span class="sxs-lookup"><span data-stu-id="839e8-136">**Edit Properties dialog box for the Mediation Server pool**</span></span>

  - <span data-ttu-id="839e8-p111">**Use all configured IP addresses** (Использовать все заданные IP-адреса). Выберите этот параметр, если требуется разрешить использование любых IP-адресов, заданных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="839e8-p111">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>

    > [!NOTE]
    > <span data-ttu-id="839e8-139">Этот параметр рекомендуется использовать для конфигураций IP версии 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="839e8-139">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

  - <span data-ttu-id="839e8-p112">**Limit service usage to selected IP addresses** (Разрешить использовать службу только указанным IP-адресам). Выберите этот параметр, чтобы указать адрес, используемый на новом сервере. Если вы выберете этот параметр, потребуется ввести значение в поле Primary IP address (Основной IP-адрес).</span><span class="sxs-lookup"><span data-stu-id="839e8-p112">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>

  - <span data-ttu-id="839e8-p113">**Primary IP address** (Основной IP-адрес). Введите IP-адрес, который будет использовать сервер для всех коммуникаций, за исключением ТСОП. Введенный IP-адрес должен соответствовать формату выбранного типа адресов.</span><span class="sxs-lookup"><span data-stu-id="839e8-p113">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>

  - <span data-ttu-id="839e8-p114">**PSTN IP address** (IP-адрес ТСОП). Укажите IP-адрес ТСОП, используемый при расположении сервера-посредника на сервере переднего плана. Введенный IP-адрес должен соответствовать формату выбранного типа адресов.</span><span class="sxs-lookup"><span data-stu-id="839e8-p114">**PSTN IP address**. Define a PSTN IP address when a Mediation Server is collocated on the Front End Server. This address must match the format of the selected address type.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="839e8-149">Поддерживаются только два сетевых адаптера на *выделенных* серверах исправлений.</span><span class="sxs-lookup"><span data-stu-id="839e8-149">We only support two network cards on *dedicated* Mediation Servers.</span></span> <span data-ttu-id="839e8-150">Если роль Ссерверя исправлений размещена на стороне переднего плана, значит, сдвоенные сетевые карты не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="839e8-150">If the Mediation Sserver role is collocated on the Front End, then dual network cards are not supported.</span></span> 

> [!NOTE]
> - <span data-ttu-id="839e8-151">Дополнительные сведения о поддерживаемых конфигурациях сетевых адаптеров в Skype для бизнеса Server 2015 можно найти в разделе [аппаратное обеспечение Skype для бизнеса server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="839e8-151">For more information about supported NIC configurations for Skype for Business Server 2015, see [Hardware for Skype for Business Server 2015](../requirements-for-your-environment/server-requirements.md#hardware-for-skype-for-business-server-2015)</span></span>
> - <span data-ttu-id="839e8-152">Дополнительные сведения о поддерживаемых конфигурациях сетевых адаптеров в Skype для бизнеса Server 2019 можно найти в разделе [аппаратное обеспечение Skype для бизнеса server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span><span class="sxs-lookup"><span data-stu-id="839e8-152">For more information about supported NIC configurations for Skype for Business Server 2019, see [Hardware for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md#hardware-for-skype-for-business-server-2019)</span></span>



## <a name="deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="839e8-153">Развертывание типов IP-адресов на пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="839e8-153">Deploy IP address types on an Edge Server</span></span>

<span data-ttu-id="839e8-154">С помощью построителя топологии выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="839e8-154">Using Topology Builder, perform the following steps:</span></span>

### <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="839e8-155">Развертывание типов IP-адресов в пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="839e8-155">To deploy IP address types on an Edge Server</span></span>

1. <span data-ttu-id="839e8-156">В построителе топологии в разделе **кластеры Edge**щелкните правой кнопкой мыши сервер в пуле и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="839e8-156">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="839e8-157">(Можно также выбрать сервер, а затем выбрать пункт **Edit Properties** (Изменить свойства) в меню **Action** (Действие).)</span><span class="sxs-lookup"><span data-stu-id="839e8-157">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2. <span data-ttu-id="839e8-158">В окне **изменения свойств** выберите конфигурацию IP-адресов, которую планируется поддерживать.</span><span class="sxs-lookup"><span data-stu-id="839e8-158">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span>

3. <span data-ttu-id="839e8-159">Для каждого выбранного типа адреса необходимо предоставить соответствующие внутренние и внешние адреса.</span><span class="sxs-lookup"><span data-stu-id="839e8-159">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>
