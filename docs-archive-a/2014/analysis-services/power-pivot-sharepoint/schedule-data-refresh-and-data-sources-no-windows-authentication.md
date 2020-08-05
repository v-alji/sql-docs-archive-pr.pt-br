---
title: Agendar a atualização de dados e fontes de dados que não dão suporte à autenticação do Windows (PowerPivot para SharePoint) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d8d875bc-7823-46b7-a939-867cefd4de12
author: minewiskan
ms.author: owend
ms.openlocfilehash: 63e37dec6f334395c0c1812c6f76d750c16c53ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574323"
---
# <a name="schedule-data-refresh-and-data-sources-that-do-not-support-windows-authentication-powerpivot-for-sharepoint"></a><span data-ttu-id="4ec2d-102">Atualização de dados de agendamento e fontes de dados que não oferecem suporte à Autenticação do Windows (PowerPivot para SharePoint)</span><span class="sxs-lookup"><span data-stu-id="4ec2d-102">Schedule Data Refresh and Data Sources That Do Not Support Windows Authentication (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="4ec2d-103">Este tópico descreve um fluxo de trabalho de atualização de dados de agendamento do PowerPivot para SharePoint que pode usar fontes de dados que **NÃO** oferecem suporte à Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-103">This topic describes a workflow of PowerPivot for SharePoint schedule data fresh that can use data sources that do **NOT** support Windows Authentication.</span></span> <span data-ttu-id="4ec2d-104">Por exemplo, fontes de dados Oracle ou IDM DB2.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-104">For example Oracle or IDM DB2 data sources.</span></span> <span data-ttu-id="4ec2d-105">As ilustrações e as etapas neste tópico fazem referência a fontes de dados Oracle, mas o mesmo fluxo de trabalho aplica-se a outras fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-105">The illustrations and steps in this topic reference Oracle data sources but the same workflow applies to other data sources.</span></span>  
  
||  
|-|  
|<span data-ttu-id="4ec2d-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2010 &#124; SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2010 &#124; SharePoint 2013.</span></span>|  
  
 <span data-ttu-id="4ec2d-107">**Visão geral:** Crie dois aplicativos de destino de repositório seguro.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-107">**Overview:** Create two Secure Store Target Applications.</span></span> <span data-ttu-id="4ec2d-108">Configure o primeiro aplicativo de destino (PowerPivotDataRefresh) para usar as credenciais do Windows.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-108">Configure the first target application (PowerPivotDataRefresh) to use Windows credentials.</span></span> <span data-ttu-id="4ec2d-109">Configure o segundo aplicativo de destino com as credenciais de uma fonte de dados que não ofereça suporte à autenticação do Windows; por exemplo, um banco de dados Oracle.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-109">Configure the second target application with the credentials for a data source that does not support windows authentication, for example, an Oracle database.</span></span> <span data-ttu-id="4ec2d-110">O segundo aplicativo de destino também usa o primeiro aplicativo de destino para a conta autônoma de atualização de dados.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-110">The second target application also uses the first target application for the unattended data refresh account.</span></span>  
  
 <span data-ttu-id="4ec2d-111">![as_powerpivot_refresh_no_windows_auth](../media/as-powerpivot-refresh-no-windows-auth.gif "as_powerpivot_refresh_no_windows_auth")</span><span class="sxs-lookup"><span data-stu-id="4ec2d-111">![as_powerpivot_refresh_no_windows_auth](../media/as-powerpivot-refresh-no-windows-auth.gif "as_powerpivot_refresh_no_windows_auth")</span></span>  
  
-   <span data-ttu-id="4ec2d-112">**(1) PowerPivotDatarefresh:** uma ID de aplicativo de destino de repositório seguro definida com a autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-112">**(1) PowerPivotDatarefresh:** A Secure Store Target Application ID that is set with windows authentication.</span></span>  
  
-   <span data-ttu-id="4ec2d-113">**(2) OracleAuthentication:** uma ID de aplicativo de destino de repositório seguro definida com as credenciais do Oracle.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-113">**(2) OracleAuthentication:** A Secure Store Target Application ID that is set with Oracle credentials.</span></span>  
  
-   <span data-ttu-id="4ec2d-114">**(3)** o aplicativo de serviço PowerPivot é configurado para usar o aplicativo de destino "PowerPivotDataRefresh" para a **conta de atualização de dados autônoma**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-114">**(3)** The PowerPivot Service application is configure to use the target application "PowerPivotDataRefresh" for the **Unattended Data Refresh Account**.</span></span>  
  
-   <span data-ttu-id="4ec2d-115">**(4)** A pasta de trabalho PowerPivot usa dados Oracle.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-115">**(4)** PowerePivot Workbook uses Oracle data.</span></span> <span data-ttu-id="4ec2d-116">As configurações de atualização da pasta de trabalho especificam a conexão da fonte de dados para usar o aplicativo de destino **(2)** para credenciais.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-116">The workbook refresh settings specify the data source connection to use the target application **(2)** for credentials.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4ec2d-117">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4ec2d-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="4ec2d-118">Existe um aplicativo de serviço PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-118">A PowerPivot Service Application exists.</span></span>  
  
-   <span data-ttu-id="4ec2d-119">Existe um aplicativo de Serviço de Repositório Seguro.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-119">A Secure Store Service Application exists.</span></span>  
  
-   <span data-ttu-id="4ec2d-120">Existe uma pasta de trabalho do Excel com um modelo de dados PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-120">An Excel workbook with a PowerPivot data model exists.</span></span>  
  
## <a name="to-create-a-target-application-id-that-uses-windows-authentication"></a><span data-ttu-id="4ec2d-121">Para criar uma ID de aplicativo de destino que usa a Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="4ec2d-121">To Create a Target Application ID that uses Windows Authentication</span></span>  
  
1.  <span data-ttu-id="4ec2d-122">Na administração central do SharePoint, clique em **gerenciar aplicativos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-122">In SharePoint Central administration, click **Manage Service Applications**.</span></span>  
  
2.  <span data-ttu-id="4ec2d-123">Clique no nome do aplicativo de Serviço de Repositório Seguro.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-123">Click the name of your secure store service application.</span></span>  
  
3.  <span data-ttu-id="4ec2d-124">Na página **Gerenciar** , clique em **Nova**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-124">On the **Manage** page, click **New**.</span></span> <span data-ttu-id="4ec2d-125">![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application")</span><span class="sxs-lookup"><span data-stu-id="4ec2d-125">![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application")</span></span>  
  
4.  <span data-ttu-id="4ec2d-126">Na página **Criar Novo Aplicativo de Destino de Repositório Seguro** , configure os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="4ec2d-126">On the **Create New Secure Store Target Application** page, configure the following values:</span></span>  
  
    -   <span data-ttu-id="4ec2d-127">**ID de Aplicativo de Destino:** PowerPivotDataRefresh.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-127">**Target Application ID:** PowerPivotDataRefresh.</span></span>  
  
    -   <span data-ttu-id="4ec2d-128">**Nome para Exibição:** PowerPivotDataRefresh.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-128">**Display Name:** PowerPivotDataRefresh.</span></span>  
  
    -   <span data-ttu-id="4ec2d-129">**Email de Contato:** ?</span><span class="sxs-lookup"><span data-stu-id="4ec2d-129">**Contact E-mail:** ?</span></span>  
  
    -   <span data-ttu-id="4ec2d-130">**Tipo de Aplicativo de Destino:** Grupo.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-130">**Target Application Type:** Group.</span></span>  
  
    -   <span data-ttu-id="4ec2d-131">**URL da Página de Aplicativo de Destino:** Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-131">**Target Application Page URL:** None.</span></span>  
  
5.  <span data-ttu-id="4ec2d-132">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-132">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="4ec2d-133">Na página Credenciais, deixe os dois nomes de campo padrão e os tipos de campo de **Nome de Usuário do Windows** e **Senha do Windows**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-133">On the Credentials page, leave the two default field names and field types for **Windows User Name** and **Windows Password**.</span></span>  
  
7.  <span data-ttu-id="4ec2d-134">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-134">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="4ec2d-135">Na página **Configurações de Associação** , adicione pelo menos um **Administrador de Aplicativo de Destino** e adicione os membros que precisam acessar o aplicativo de destino.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-135">On the **Membership Settings** page, add at least one **Target Application Administrator** and then add members that need access to the target application.</span></span>  
  
9. <span data-ttu-id="4ec2d-136">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-136">Click **OK**.</span></span>  
  
10. <span data-ttu-id="4ec2d-137">Uma nova ID de aplicativo de destino será adicionada à lista.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-137">The new Target Application ID is added to the list.</span></span> <span data-ttu-id="4ec2d-138">Selecione a ID do aplicativo de destino e clique em **definir credenciais**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span><span class="sxs-lookup"><span data-stu-id="4ec2d-138">Select the Target application ID and click **Set Credentials**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span></span>  
  
11. <span data-ttu-id="4ec2d-139">Digite o nome de usuário do Windows e a senha do Windows, e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-139">Type the Windows User Name and Windows Password and then click **OK**.</span></span>  
  
## <a name="to-create-a-target-application-id-that-uses-oracle-credentials"></a><span data-ttu-id="4ec2d-140">Para criar uma ID de aplicativo de destino que usa as credenciais do Oracle</span><span class="sxs-lookup"><span data-stu-id="4ec2d-140">To Create a Target Application ID that uses Oracle credentials</span></span>  
  
1.  <span data-ttu-id="4ec2d-141">Na administração central do SharePoint, clique em **gerenciar aplicativos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-141">In SharePoint Central administration, click **Manage Service Applications**.</span></span>  
  
2.  <span data-ttu-id="4ec2d-142">Clique no nome do aplicativo de Serviço de Repositório Seguro.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-142">Click the name of your Secure Store Service application.</span></span>  
  
3.  <span data-ttu-id="4ec2d-143">Na página **gerenciar** , clique em **novo**![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application").</span><span class="sxs-lookup"><span data-stu-id="4ec2d-143">On the **Manage** page, click **New**![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application").</span></span>  
  
4.  <span data-ttu-id="4ec2d-144">Na página **Criar Novo Aplicativo de Destino de Repositório Seguro** , configure os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="4ec2d-144">On the **Create New Secure Store Target Application** page, configure the following values:</span></span>  
  
    -   <span data-ttu-id="4ec2d-145">**ID do Aplicativo de Destino:** OracleAuthentication.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-145">**Target Application ID:** OracleAuthentication.</span></span>  
  
    -   <span data-ttu-id="4ec2d-146">**Nome para Exibição:** OracleAuthentication.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-146">**Display Name:** OracleAuthentication.</span></span>  
  
    -   <span data-ttu-id="4ec2d-147">**Email de Contato:** ?</span><span class="sxs-lookup"><span data-stu-id="4ec2d-147">**Contact E-mail:** ?</span></span>  
  
    -   <span data-ttu-id="4ec2d-148">**Tipo de Aplicativo de Destino:** Grupo.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-148">**Target Application Type:** Group.</span></span>  
  
    -   <span data-ttu-id="4ec2d-149">**URL da Página de Aplicativo de Destino:** Nenhuma.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-149">**Target Application Page URL:** None.</span></span>  
  
5.  <span data-ttu-id="4ec2d-150">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-150">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="4ec2d-151">Na página **credenciais** , altere o nome do primeiro campo para `Oracle User ID` e altere o **tipo de campo** para `User Name` .</span><span class="sxs-lookup"><span data-stu-id="4ec2d-151">On the **Credentials** page, change the first field name to `Oracle User ID` and change the **Field Type** to `User Name`.</span></span>  
  
     <span data-ttu-id="4ec2d-152">Altere o segundo nome de campo para `Oracle Password` e o **tipo de campo** para `Password` .</span><span class="sxs-lookup"><span data-stu-id="4ec2d-152">Change the second field name to `Oracle Password` and the **Field Type** to `Password`.</span></span>  
  
7.  <span data-ttu-id="4ec2d-153">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-153">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="4ec2d-154">Na página **Configurações de Associação** , adicione pelo menos um **Administrador de Aplicativo de Destino** e adicione os membros que precisam acessar o aplicativo de destino.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-154">On the **Membership Settings** page, add at least one **Target Application Administrator** and then add members that need access to the target application.</span></span>  
  
9. <span data-ttu-id="4ec2d-155">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-155">Click **OK**.</span></span>  
  
10. <span data-ttu-id="4ec2d-156">Uma nova ID de aplicativo de destino será adicionada à lista.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-156">The new Target Application ID is added to the list.</span></span> <span data-ttu-id="4ec2d-157">Selecione a ID do aplicativo de destino e clique em **definir credenciais**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span><span class="sxs-lookup"><span data-stu-id="4ec2d-157">Select the Target application ID and click **Set Credentials**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span></span>  
  
11. <span data-ttu-id="4ec2d-158">Digite a ID do Usuário Oracle e a Senha Oracle, e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-158">Type the Oracle User ID and Oracle Password and then click **OK**.</span></span>  
  
 <span data-ttu-id="4ec2d-159">Para obter mais informações, consulte a seção "para criar um aplicativo de destino para SQL Server autenticação" em [usar repositório seguro com autenticação SQL Server (SharePoint Server 2013)](https://technet.microsoft.com/library/gg298949.aspx) ( https://technet.microsoft.com/library/gg298949.aspx) .</span><span class="sxs-lookup"><span data-stu-id="4ec2d-159">For more information, see section "To Create a target application for SQL Server Authentication" in [Use Secure Store with SQL Server Authentication (SharePoint Server 2013)](https://technet.microsoft.com/library/gg298949.aspx) (https://technet.microsoft.com/library/gg298949.aspx).</span></span>  
  
## <a name="to-configure-the-powerpivot-service-application"></a><span data-ttu-id="4ec2d-160">Para configurar o aplicativo de serviço PowerPivot</span><span class="sxs-lookup"><span data-stu-id="4ec2d-160">To Configure the PowerPivot Service Application</span></span>  
  
1.  <span data-ttu-id="4ec2d-161">Na Administração Central do SharePoint, clique em Gerenciar Aplicativos de Serviço.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-161">In SharePoint central administration, click Manage Service Applications.</span></span>  
  
2.  <span data-ttu-id="4ec2d-162">Clique no nome do aplicativo de serviço PowerPivot, por exemplo, "aplicativo de serviço PowerPivot padrão".</span><span class="sxs-lookup"><span data-stu-id="4ec2d-162">Click the name of your PowerPivot Service Application, for example "Default PowerPivot Service Application".</span></span>  
  
3.  <span data-ttu-id="4ec2d-163">Clique em **Definir configurações do aplicativo de serviço** na seção Ações.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-163">Click **Configure service application settings** in the Actions section.</span></span>  
  
4.  <span data-ttu-id="4ec2d-164">Na seção **atualização de dados** , defina a **conta de atualização de dados autônoma do PowerPivot**para `PowerPivotDataRefresh` e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-164">In the **Data Refresh** section, set the **PowerPivot Unattended Data Refresh Account**to`PowerPivotDataRefresh` and then click **OK**.</span></span>  
  
     <span data-ttu-id="4ec2d-165">![as_powerpivot_refresh_new_refresh_acount](../media/as-powerpivot-refresh-new-refresh-acount.gif "as_powerpivot_refresh_new_refresh_acount")</span><span class="sxs-lookup"><span data-stu-id="4ec2d-165">![as_powerpivot_refresh_new_refresh_acount](../media/as-powerpivot-refresh-new-refresh-acount.gif "as_powerpivot_refresh_new_refresh_acount")</span></span>  
  
## <a name="to-configure-the-workbook"></a><span data-ttu-id="4ec2d-166">Para configurar a pasta de trabalho</span><span class="sxs-lookup"><span data-stu-id="4ec2d-166">To configure the workbook</span></span>  
  
1.  <span data-ttu-id="4ec2d-167">Navegue até a pasta de trabalho na Galeria PowerPivot e clique em **gerenciar atualização de dados**![as_powerpivot_refresh_manage_reresh](../media/as-powerpivot-refresh-manage-reresh.gif "as_powerpivot_refresh_manage_reresh").</span><span class="sxs-lookup"><span data-stu-id="4ec2d-167">Browse to your workbook in the PowerPivot Gallery and click **Manage Data Refresh**![as_powerpivot_refresh_manage_reresh](../media/as-powerpivot-refresh-manage-reresh.gif "as_powerpivot_refresh_manage_reresh").</span></span>  
  
2.  <span data-ttu-id="4ec2d-168">Se a página **Histórico de Atualização de Dados** for exibida, clique em **Configurar Agendamento**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-168">If you see the **Data Refresh History** page, click **Configure Schedule**.</span></span>  
  
3.  <span data-ttu-id="4ec2d-169">Clique em **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-169">Click **Enable**.</span></span>  
  
4.  <span data-ttu-id="4ec2d-170">Clique em **Também atualizar o mais rápido possível**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-170">Click **Also Refresh as soon as possible**.</span></span>  
  
5.  <span data-ttu-id="4ec2d-171">Na seção **Credenciais** , clique em **Usar a conta de atualização de dados configurada pelo administrador**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-171">In the **Credentials** section, click **Use the Data refresh account configured by the administrator**.</span></span>  
  
6.  <span data-ttu-id="4ec2d-172">Limpe **Todas as fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-172">Clear **All data sources**.</span></span>  
  
7.  <span data-ttu-id="4ec2d-173">Selecione **Atualizar** para a fonte de dados que usa os dados Oracle.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-173">Select **Refresh** for the data source that uses the Oracle data.</span></span> <span data-ttu-id="4ec2d-174">O nome da fonte de dados pode ser alterado no Microsoft Excel através do menu **Dados**, **Conexões**, **Propriedades** .</span><span class="sxs-lookup"><span data-stu-id="4ec2d-174">The name of the data source name can be changed in Microsoft Excel in the **Data**, **Connections**, **Properties** menu.</span></span>  
  
8.  <span data-ttu-id="4ec2d-175">Abaixo da sua fonte de dados, selecione **Usar Agendamento Padrão**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-175">Under your data source, Select **Use Default Schedule**.</span></span>  
  
9. <span data-ttu-id="4ec2d-176">Selecione **Conecte-se usando as credenciais salvas no SSS (Serviço de Repositório Seguro) para fazer logon na fonte de dados. Insira a ID usada para pesquisar as credenciais na caixa ID do SSS**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-176">Select **Connect using the credentials saved in Secure Store Service (SSS) to log on to the data source. Enter the ID used to look up the credentials in the SSS ID box**.</span></span>  
  
10. <span data-ttu-id="4ec2d-177">Na caixa **ID:** , digite `OracleAuthentication` .</span><span class="sxs-lookup"><span data-stu-id="4ec2d-177">In the **ID:** box, type `OracleAuthentication`.</span></span>  
  
11. <span data-ttu-id="4ec2d-178">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-178">Click **OK**.</span></span>  
  
     <span data-ttu-id="4ec2d-179">Se uma mensagem de erro semelhante a `The provided Secure Store target application is either incorrectly configured or does not exist`for exibida.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-179">If you see an error message similar to: `The provided Secure Store target application is either incorrectly configured or does not exist`.</span></span>  
  
     <span data-ttu-id="4ec2d-180">Há duas soluções comuns:</span><span class="sxs-lookup"><span data-stu-id="4ec2d-180">The two common solutions are:</span></span>  
  
    -   <span data-ttu-id="4ec2d-181">Verifique se a ID do aplicativo de destino está correta.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-181">Verify that the Target Application ID is correct.</span></span>  
  
    -   <span data-ttu-id="4ec2d-182">Verifique se você definiu as credenciais do aplicativo de destino.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-182">Verify that you set credentials for the Target Application.</span></span>  
  
## <a name="to-verify-data-refresh-with-the-new-authentication"></a><span data-ttu-id="4ec2d-183">Para verificar a atualização de dados com a nova autenticação</span><span class="sxs-lookup"><span data-stu-id="4ec2d-183">To Verify Data Refresh with the new authentication</span></span>  
 <span data-ttu-id="4ec2d-184">Ao clicar em **OK**, você verá a página **Histórico de Atualização** .</span><span class="sxs-lookup"><span data-stu-id="4ec2d-184">When you click **ok**, you see the **Refresh History** page.</span></span> <span data-ttu-id="4ec2d-185">Em alguns minutos, você verá um novo item no histórico de atualização porque, na etapa anterior, selecionou **Também atualizar o mais rápido possível**.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-185">Within a few minutes, you should see a new item in the refresh history because in the previous steps you selected **Also Refresh as soon as possible**.</span></span> <span data-ttu-id="4ec2d-186">O valor padrão do **Trabalho de Timer da Atualização de Dados PowerPivot** é um minuto.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-186">The default value for the timer job **PowerPivot Data Refresh Timer Job** is 1 minute.</span></span> <span data-ttu-id="4ec2d-187">Se um novo item não aparecer no histórico de atualização, aguarde alguns minutos e atualize o navegador.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-187">If you do not see a new item in the refresh history, wait a few minutes and refresh your browser.</span></span> <span data-ttu-id="4ec2d-188">Se, ainda assim, o novo item não aparecer, verifique o valor atual do trabalho de timer.</span><span class="sxs-lookup"><span data-stu-id="4ec2d-188">If you still do not see the new item, verify the current value of the timer job.</span></span>  
  
## <a name="more-information"></a><span data-ttu-id="4ec2d-189">Mais informações</span><span class="sxs-lookup"><span data-stu-id="4ec2d-189">More Information</span></span>  
  
-   <span data-ttu-id="4ec2d-190">[Configurar o Serviço de Repositório Seguro no SharePoint 2013](https://technet.microsoft.com/library/ee806866.aspx).</span><span class="sxs-lookup"><span data-stu-id="4ec2d-190">[Configure the Secure Store Service in SharePoint 2013](https://technet.microsoft.com/library/ee806866.aspx).</span></span>  
  
-   <span data-ttu-id="4ec2d-191">Consulte a seção "atualização de dados agendada" da [atualização de dados PowerPivot com o SharePoint 2013 e SQL Server 2012 SP1 (Analysis Services)](https://msdn.microsoft.com/library/jj879294.aspx#bkmk_windows_auth_interactive_data_refresh).</span><span class="sxs-lookup"><span data-stu-id="4ec2d-191">See the "Scheduled Data Refresh" section of [PowerPivot Data Refresh with SharePoint 2013 and SQL Server 2012 SP1 (Analysis Services)](https://msdn.microsoft.com/library/jj879294.aspx#bkmk_windows_auth_interactive_data_refresh).</span></span>  
  
  
