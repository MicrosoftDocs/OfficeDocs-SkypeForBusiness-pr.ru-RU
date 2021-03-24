---
title: Подключение приложения для пациентов к Azure API для FHIR
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Узнайте, как подключить приложение "Пациенты" в Microsoft Teams к Azure API для FHIR (ресурсы по быстрой организации здравоохранения).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e06e422765c1d1d633414d24dff48e2801067f15
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096271"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="2ba3b-103">Подключение приложения для пациентов к Azure API для FHIR</span><span class="sxs-lookup"><span data-stu-id="2ba3b-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="2ba3b-104">С 30 октября 2020 г. приложение "Пациенты" устарело и заменено приложением [Lists](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) в Teams.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="2ba3b-105">Данные приложения "Пациенты" хранятся в почтовом ящике группы Office 365, на которой основана команда.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="2ba3b-106">Все данные, связанные с приложением "Пациенты", сохраняются в этой группе, но больше недоступны в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="2ba3b-107">Пользователи могут повторно создать свои списки с помощью приложения [Lists](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="2ba3b-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="2ba3b-108">С помощью приложения Lists медицинские бригады вашей организации здравоохранения могут создавать списки пациентов для различных сценариев: от обходов и собраний междисциплинарных команд до общего наблюдения за пациентами.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="2ba3b-109">Ознакомьтесь с шаблоном "Пациенты" в приложении Lists, чтобы начать работу.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="2ba3b-110">Дополнительные сведения об управлении приложением Lists в организации см. в статье [Управление приложением Lists](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="2ba3b-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="2ba3b-111">Чтобы разрешить приложению "Пациенты" в Microsoft Teams доступ к экземпляру Azure API для FHIR, выполните указанные здесь действия.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-111">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="2ba3b-112">В этой статье предполагается, что в вашем клиенте настроен экземпляр Azure API для [FHIR.](https://azure.microsoft.com/services/azure-api-for-fhir/)</span><span class="sxs-lookup"><span data-stu-id="2ba3b-112">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="2ba3b-113">Если вы еще не создали экземпляр Azure API для FHIR в своем клиенте, см. краткое краткое видео: развертывание Azure API для [FHIR с помощью портала Azure.](/azure/healthcare-apis/fhir-paas-portal-quickstart)</span><span class="sxs-lookup"><span data-stu-id="2ba3b-113">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>

1. <span data-ttu-id="2ba3b-114">Щелкните [здесь,](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) чтобы предоставить администратору разрешение для приложения "Пациенты".</span><span class="sxs-lookup"><span data-stu-id="2ba3b-114">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="2ba3b-115">При запросе войдите с учетными данными администратора  клиента или глобального администратора, а затем нажмите кнопку "Принять", чтобы предоставить необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-115">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![Снимок экрана: запрос разрешений для приложения "Пациенты"](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="2ba3b-117">После того как вы примете приглашение, закроем окно.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-117">After you accept, close the window.</span></span> <span data-ttu-id="2ba3b-118">Вы увидите страницу, которая может выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="2ba3b-118">You'll see a page that may look like this.</span></span> <span data-ttu-id="2ba3b-119">Сообщение об ошибке можно игнорировать на странице.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-119">You can ignore the error message on the page.</span></span> <span data-ttu-id="2ba3b-120">Это не означает, что вы получили согласие.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-120">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="2ba3b-121">(Мы работаем над более удобной страницей для этого URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-121">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="2ba3b-122">Следите за обновлениями!)</span><span class="sxs-lookup"><span data-stu-id="2ba3b-122">Stay tuned!)</span></span>

    ![Снимок экрана: запрос разрешений для приложения "Пациенты"](../../media/patients-app-permissions-request-granted.png)

2. <span data-ttu-id="2ba3b-124">Войте на портал [Azure с](https://portal.azure.com) учетными данными администратора.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-124">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="2ba3b-125">В области навигации слева выберите **Azure Active Directory,** а затем — **"Корпоративные приложения".**</span><span class="sxs-lookup"><span data-stu-id="2ba3b-125">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>

    <span data-ttu-id="2ba3b-126">Найди строку "Пациенты" **и** скопируйте  значение в столбце "ИД объекта" в буфер обмена.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-126">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>

    ![Снимок экрана: строка "Пациенты" на портале Azure](../../media/patients-app-azure-portal-object-id.png)

4. <span data-ttu-id="2ba3b-128">Перейдите к экземпляру ресурса Azure API для FHIR, к которому вы хотите подключить приложение "Пациенты" (посредством поиска или просмотра ресурсов), а затем откройте параметры этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-128">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Снимок экрана: параметры экземпляра Azure API для FHIR на портале Azure](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="2ba3b-130">Нажмите **кнопку "Проверка** подлинности" и в поле "Разрешенные  ИД объектов" в поле "Разрешенные" в поле "ИД объекта", скопированные на шаге 3.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-130">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="2ba3b-131">Это позволит приложению "Пациенты" получать доступ к серверу FHIR.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-131">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="2ba3b-132">После вметки ИД объекта Azure Active Directory проверит его, и рядом с его иным объектом появится зеленая метка.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-132">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Снимок экрана: параметры проверки подлинности на портале Azure](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="2ba3b-134">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-134">Click **Save**.</span></span> <span data-ttu-id="2ba3b-135">При этом экземпляр будет раздвоен, что может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-135">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="2ba3b-136">Щелкните **"Обзор"** и скопируйте URL-адрес с конечной точки **метаданных FHIR.**</span><span class="sxs-lookup"><span data-stu-id="2ba3b-136">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="2ba3b-137">Удалите тег метаданных, чтобы получить URL-адрес сервера FHIR.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-137">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="2ba3b-138">Например, `https://test02-teamshealth.azurehealthcareapis.com/` .</span><span class="sxs-lookup"><span data-stu-id="2ba3b-138">For example, `https://test02-teamshealth.azurehealthcareapis.com/`.</span></span>

    ![конечная точка метаданных на портале Azure](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="2ba3b-140">В Teams перейдите в экземпляр приложения "Пациенты", загруженный в группу,  щелкните "Параметры", а затем в поле "Ссылка" введите URL-адрес конечной точки сервера FHIR.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-140">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="2ba3b-141">Затем нажмите **кнопку** "Подключиться", чтобы установить подключение, а затем найдите и добавьте пациентов в список.</span><span class="sxs-lookup"><span data-stu-id="2ba3b-141">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![ <span data-ttu-id="2ba3b-142">Параметры приложения "Пациенты" в Teams</span><span class="sxs-lookup"><span data-stu-id="2ba3b-142">Patients app settings in Teams</span></span>](../../media/patients-app-teams.png)

    <span data-ttu-id="2ba3b-143">Если на этом этапе вы получаете сообщение об ошибке при подключении к Teams, отправьте подробный снимок экрана, журналы из [Fiddler](https://www.telerik.com/download/fiddler) и другие действия повторного действия в сообщении электронной почты с строкой темы "Приложение для пациентов — устранение неполадок в режиме EMR" в [teamsforhealthcare@service.microsoft.com.](mailto:teamsforhealthcare@service.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="2ba3b-143">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2ba3b-144">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="2ba3b-144">Related topics</span></span>

- [<span data-ttu-id="2ba3b-145">Обзор приложения для пациентов</span><span class="sxs-lookup"><span data-stu-id="2ba3b-145">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="2ba3b-146">Интеграция электронных историй болезни в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2ba3b-146">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)