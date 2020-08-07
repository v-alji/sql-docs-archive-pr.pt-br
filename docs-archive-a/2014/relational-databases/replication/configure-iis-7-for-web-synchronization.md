---
title: Configurar o IIS 7 para sincronização da Web | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- IIS 7 server configuration [SQL Server replication]
- Web synchronization, IIS 7 servers
ms.assetid: c201fe2c-0a76-44e5-a233-05e14cd224a6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 65b5aa1ea0d314a9675b1c1b90b688d2990e6d24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87584121"
---
# <a name="configure-iis-7-for-web-synchronization"></a><span data-ttu-id="4cee7-102">Configurar o IIS 7 para sincronização da Web</span><span class="sxs-lookup"><span data-stu-id="4cee7-102">Configure IIS 7 for Web Synchronization</span></span>
  <span data-ttu-id="4cee7-103">Os procedimentos deste tópico guiarão você pelo processo de configuração manual do Serviços de Informações da Internet (IIS) versão 7 e mais recentes da [!INCLUDE[msCoName](../../includes/msconame-md.md)] para uso com sincronização da Web para replicação de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="4cee7-103">The procedures in this topic will guide you through the process of manually configuring [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) version 7 and higher for use with Web synchronization for merge replication.</span></span> 
  
 <span data-ttu-id="4cee7-104">A configuração do IIS 7 é a primeira das três etapas necessárias para habilitar a sincronização da Web.</span><span class="sxs-lookup"><span data-stu-id="4cee7-104">Configuring IIS 7 is the first of three steps needed to enable Web synchronization.</span></span>  
  
 <span data-ttu-id="4cee7-105">Para obter uma visão geral de todo o processo de configuração, consulte [Configurar Sincronização da Web](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="4cee7-105">For an overview of the entire configuration process, see [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4cee7-106">Certifique-se de que seu aplicativo use apenas versões [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] ou posteriores e que as versões anteriores do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] não estejam instaladas no servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="4cee7-106">Make sure that your application uses only [!INCLUDE[dnprdnlong](../../includes/dnprdnlong-md.md)] or later versions, and that earlier versions of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] are not installed on the IIS server.</span></span> <span data-ttu-id="4cee7-107">Versões anteriores do [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] podem causar erros, como: "Formato inválido de uma mensagem durante a sincronização da Web.</span><span class="sxs-lookup"><span data-stu-id="4cee7-107">Earlier versions of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] can cause errors, such as: "The format of a message during Web synchronization was invalid.</span></span> <span data-ttu-id="4cee7-108">Verifique se os componentes de replicação estão adequadamente configurados no servidor Web".</span><span class="sxs-lookup"><span data-stu-id="4cee7-108">Ensure that replication components are properly configured at the Web server."</span></span>  
  
 <span data-ttu-id="4cee7-109">Para usar a sincronização da Web, é necessário configurar o IIS 7 concluindo as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="4cee7-109">To use Web synchronization, you must configure IIS 7 by completing the following steps.</span></span> <span data-ttu-id="4cee7-110">Cada etapa é descrita em detalhes neste tópico.</span><span class="sxs-lookup"><span data-stu-id="4cee7-110">Each step is described in detail in this topic.</span></span>  
  
1.  <span data-ttu-id="4cee7-111">Instale e configure o [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener no computador que executa o IIS.</span><span class="sxs-lookup"><span data-stu-id="4cee7-111">Install and configure the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener on the computer that is running IIS.</span></span>  
  
2.  <span data-ttu-id="4cee7-112">Configure o protocolo SSL.</span><span class="sxs-lookup"><span data-stu-id="4cee7-112">Configure Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="4cee7-113">O SSL é necessário para a comunicação entre o IIS e todos os assinantes.</span><span class="sxs-lookup"><span data-stu-id="4cee7-113">SSL is required for communication between IIS and all subscribers.</span></span>  
  
3.  <span data-ttu-id="4cee7-114">Configure a autenticação IIS.</span><span class="sxs-lookup"><span data-stu-id="4cee7-114">Configure IIS authentication.</span></span>  
  
4.  <span data-ttu-id="4cee7-115">Configure uma conta e defina as permissões para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener Replicação.</span><span class="sxs-lookup"><span data-stu-id="4cee7-115">Configure an account and set permissions for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener.</span></span>  
  
## <a name="installing-the-sql-server-replication-listener"></a><span data-ttu-id="4cee7-116">Instalando o SQL Server Replication Listener</span><span class="sxs-lookup"><span data-stu-id="4cee7-116">Installing the SQL Server Replication Listener</span></span>  

<span data-ttu-id="4cee7-117">Há suporte para sincronização da Web no IIS, a partir da versão 5.0.</span><span class="sxs-lookup"><span data-stu-id="4cee7-117">Web synchronization is supported on IIS, beginning with version 5.0.</span></span> <span data-ttu-id="4cee7-118">O Assistente para Configurar Sincronização da Web do IIS versão 5 e 6 não está disponível com o IIS versão 7.0 e superior.</span><span class="sxs-lookup"><span data-stu-id="4cee7-118">The Configure Web Synchronization Wizard of IIS version 5 and 6, is not available with IIS version 7.0 and higher.</span></span> <span data-ttu-id="4cee7-119">**A partir do SQL Server 2012, para usar o componente de sincronização da Web no servidor IIS, você deve instalar o SQL Server com replicação. Essa pode ser a edição gratuita do SQL Server Express.**</span><span class="sxs-lookup"><span data-stu-id="4cee7-119">**Beginning with SQL Server 2012, to use the web sync component on IIS server, you should install SQL Server with replication. This can be the free SQL Server Express edition.**</span></span>
  
#### <a name="to-install-and-configure-the-sql-server-replication-listener"></a><span data-ttu-id="4cee7-120">Para instalar e configurar o SQL Server Replication Listener</span><span class="sxs-lookup"><span data-stu-id="4cee7-120">To install and configure the SQL Server Replication Listener</span></span>  
  
1. <span data-ttu-id="4cee7-121">Instale a replicação do SQL Server no computador com IIS.</span><span class="sxs-lookup"><span data-stu-id="4cee7-121">Install SQL Server replication on the IIS computer.</span></span>

2.  <span data-ttu-id="4cee7-122">Crie um novo diretório de arquivos para replisapi.dll no computador que está executando o IIS.</span><span class="sxs-lookup"><span data-stu-id="4cee7-122">Create a new file directory for replisapi.dll on the computer that is running IIS.</span></span> <span data-ttu-id="4cee7-123">Você poderá criar o diretório onde desejar, mas é recomendável criá-lo no diretório \<*drive*>:\Inetpub.</span><span class="sxs-lookup"><span data-stu-id="4cee7-123">You can create the directory wherever you want, but we recommend that you create the directory under the \<*drive*>:\Inetpub directory.</span></span> <span data-ttu-id="4cee7-124">Por exemplo, crie o diretório \<*drive*>:\Inetpub\SQLReplication\\.</span><span class="sxs-lookup"><span data-stu-id="4cee7-124">For example, create the directory \<*drive*>:\Inetpub\SQLReplication\\.</span></span>  
  
3.  <span data-ttu-id="4cee7-125">Copie replisapi.dll do diretório [!INCLUDE[ssInstallPathVar](../../includes/ssinstallpathvar-md.md)]com\ para o diretório de arquivos que você criou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="4cee7-125">Copy replisapi.dll from the directory [!INCLUDE[ssInstallPathVar](../../includes/ssinstallpathvar-md.md)]com\ to the file directory that you created in step 1.</span></span>  
  
4.  <span data-ttu-id="4cee7-126">Registre replisapi.dll:</span><span class="sxs-lookup"><span data-stu-id="4cee7-126">Register replisapi.dll:</span></span>  
  
    1.  <span data-ttu-id="4cee7-127">Clique em **Iniciar**e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-127">Click **Start**, and then click **Run**.</span></span> <span data-ttu-id="4cee7-128">Na caixa **abrir** , digite `cmd` e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-128">In the **Open** box, enter `cmd`, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="4cee7-129">No diretório criado na etapa 1, execute o comando a seguir:</span><span class="sxs-lookup"><span data-stu-id="4cee7-129">In the directory created in step 1, execute the following command:</span></span>  
  
         `regsvr32 replisapi.dll`  
  
5.  <span data-ttu-id="4cee7-130">Crie um novo site para replicação ou use um site existente.</span><span class="sxs-lookup"><span data-stu-id="4cee7-130">Create a new Web site for replication or use an existing site.</span></span> <span data-ttu-id="4cee7-131">Esse site será acessado pelos componentes de replicação durante a sincronização.</span><span class="sxs-lookup"><span data-stu-id="4cee7-131">This Web site will be accessed by replication components during synchronization.</span></span> <span data-ttu-id="4cee7-132">Os procedimentos deste tópico pressupõem o Site Padrão.</span><span class="sxs-lookup"><span data-stu-id="4cee7-132">Procedures in this topic will assume the Default Web Site.</span></span> <span data-ttu-id="4cee7-133">Para obter mais informações sobre como criar sites, consulte a documentação do IIS</span><span class="sxs-lookup"><span data-stu-id="4cee7-133">For more information about how to create Web sites, see the IIS documentation</span></span>  
  
6.  <span data-ttu-id="4cee7-134">Crie um diretório virtual em IIS.</span><span class="sxs-lookup"><span data-stu-id="4cee7-134">Create a virtual directory in IIS.</span></span> <span data-ttu-id="4cee7-135">O diretório virtual deve ser criado no site criado na etapa 4 e deve ser mapeado para o diretório que foi criado na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="4cee7-135">The virtual directory should be created under the Web site that you created in step 4 and map it to the directory created in step 1.</span></span> <span data-ttu-id="4cee7-136">Seja o mais restritivo possível ao atribuir a esse diretório.</span><span class="sxs-lookup"><span data-stu-id="4cee7-136">Be as restrictive as possible when you assign permissions to this directory.</span></span> <span data-ttu-id="4cee7-137">Você deve selecionar pelo menos as permissões de **Leitura** e **Execução** .</span><span class="sxs-lookup"><span data-stu-id="4cee7-137">You must select at least **Read** and **Execute** permissions.</span></span>  
  
    1.  <span data-ttu-id="4cee7-138">No **Gerenciador dos Serviços de Informações da Internet (IIS)** , no painel **Conexões** , clique com o botão direito em **Site Padrão**e selecione **Adicionar Diretório virtual**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-138">In **Internet Information Services (IIS) Manager**, in the **Connections** pane, right-click **Default Web Site**, and then select **Add Virtual Directory**.</span></span>  
  
    2.  <span data-ttu-id="4cee7-139">Para **alias**, insira `SQLReplication` .</span><span class="sxs-lookup"><span data-stu-id="4cee7-139">For **Alias**, enter `SQLReplication`.</span></span>  
  
    3.  <span data-ttu-id="4cee7-140">Para **Caminho físico**, insira **\<drive>:\Inetpub\SQLReplication\\** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-140">For **Physical Path**, enter **\<drive>:\Inetpub\SQLReplication\\**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="4cee7-141">Configure o IIS para habilitar a execução de replisapi.dll.</span><span class="sxs-lookup"><span data-stu-id="4cee7-141">Configure IIS to enable replisapi.dll to execute.</span></span>  
  
    1.  <span data-ttu-id="4cee7-142">No **Gerenciador dos Serviços de Informações da Internet (IIS)** , clique em **Site Padrão**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-142">In **Internet Information Services (IIS) Manager**, click **Default Web Site**.</span></span>  
  
    2.  <span data-ttu-id="4cee7-143">No painel central, clique em **Mapeamentos do Manipulador**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-143">In the center pane, click **Handler Mappings**.</span></span>  
  
    3.  <span data-ttu-id="4cee7-144">No painel **Ações** , clique em **Adicionar Mapeamento de Módulo**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-144">In the **Actions** pane, click **Add Module Mapping**.</span></span>  
  
    4.  <span data-ttu-id="4cee7-145">Para caminho de **solicitação** , insira `replisapi.dll` .</span><span class="sxs-lookup"><span data-stu-id="4cee7-145">For **Request** Path, enter `replisapi.dll`.</span></span>  
  
    5.  <span data-ttu-id="4cee7-146">Na lista suspensa **Módulo** , selecione **IsapiModule**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-146">From the **Module** drop-down list, select **IsapiModule**.</span></span>  
  
    6.  <span data-ttu-id="4cee7-147">Para **Executável**, insira **\<drive>:\Inetpub\SQLReplication\replisapi.dll**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-147">For **Executable**, enter **\<drive>:\Inetpub\SQLReplication\replisapi.dll**.</span></span>  
  
    7.  <span data-ttu-id="4cee7-148">Para **Nome**, insira `Replisapi`.</span><span class="sxs-lookup"><span data-stu-id="4cee7-148">For **Name**, enter `Replisapi`.</span></span>  
  
    8.  <span data-ttu-id="4cee7-149">Clique no botão **Restrições da Solicitação** , clique na guia **Acesso** e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-149">Click the **Request Restrictions** button, click the **Access** tab, and then click **Execute**.</span></span>  
  
    9. <span data-ttu-id="4cee7-150">Clique em **OK** para fechar a caixa de diálogo **Restrições da Solicitação** e clique em **OK** novamente para fechar a caixa de diálogo **Adicionar Mapeamento de Módulo** .</span><span class="sxs-lookup"><span data-stu-id="4cee7-150">Click **OK** to close the **Request Restrictions** dialog box, and then click **OK** again to close the **Add Module Mapping** dialog box.</span></span> <span data-ttu-id="4cee7-151">Quando for solicitado a permitir a extensão de ISAPI, clique em **Sim** para adicionar a extensão.</span><span class="sxs-lookup"><span data-stu-id="4cee7-151">When you are prompted to allow the ISAPI extension, click **Yes** to add the extension.</span></span>  
  
    10. <span data-ttu-id="4cee7-152">Verifique se Replisapi.dll está listado sob os mapeamentos do manipulador **Habilitados** .</span><span class="sxs-lookup"><span data-stu-id="4cee7-152">Verify that Replisapi.dll is listed under the **Enabled** handler mappings.</span></span> <span data-ttu-id="4cee7-153">Se ele estiver na lista **Desabilitados** , clique com o botão direito do mouse na entrada Replisapi e clique em **Editar Permissões de Recurso**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-153">If it is in the **Disabled** list, right-click the Replisapi entry and then click **Edit Feature Permissions**.</span></span> <span data-ttu-id="4cee7-154">Marque a caixa de seleção **Executar** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-154">Check the **Execute** box, and then click **OK**.</span></span>  
  
## <a name="configuring-iis-authentication"></a><span data-ttu-id="4cee7-155">Configurando a Autenticação IIS</span><span class="sxs-lookup"><span data-stu-id="4cee7-155">Configuring IIS Authentication</span></span>  
 <span data-ttu-id="4cee7-156">Quando os computadores assinantes se conectam ao IIS, o IIS deve autenticar os assinantes para que eles possam acessar recursos e processos.</span><span class="sxs-lookup"><span data-stu-id="4cee7-156">When subscriber computers connect to IIS, IIS must authenticate the subscribers before they can access resources and processes.</span></span> <span data-ttu-id="4cee7-157">A autenticação pode ser aplicada para o site da Web inteiro ou para o diretório virtual que você criou.</span><span class="sxs-lookup"><span data-stu-id="4cee7-157">Authentication can be applied to the whole Web site or to the virtual directory that you created.</span></span>  
  
 <span data-ttu-id="4cee7-158">É recomendável usar a Autenticação Básica com SSL.</span><span class="sxs-lookup"><span data-stu-id="4cee7-158">We recommend that you use Basic Authentication with SSL.</span></span> <span data-ttu-id="4cee7-159">A SSL é necessária, independentemente do tipo de autenticação usado.</span><span class="sxs-lookup"><span data-stu-id="4cee7-159">SSL is required, regardless of the type of authentication that is used.</span></span>  
  
 <span data-ttu-id="4cee7-160">É recomendável usar a Autenticação Básica com SSL.</span><span class="sxs-lookup"><span data-stu-id="4cee7-160">We recommend that you use Basic Authentication with SSL.</span></span> <span data-ttu-id="4cee7-161">A SSL é necessária, independentemente do tipo de autenticação usado.</span><span class="sxs-lookup"><span data-stu-id="4cee7-161">SSL is required, regardless of the type of authentication that is used.</span></span>  
  
#### <a name="to-configure-iis-authentication"></a><span data-ttu-id="4cee7-162">Para configurar a Autenticação IIS</span><span class="sxs-lookup"><span data-stu-id="4cee7-162">To Configure IIS Authentication</span></span>  
  
1.  <span data-ttu-id="4cee7-163">No **Gerenciador dos Serviços de Informações da Internet (IIS)** , clique em **Site Padrão**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-163">In **Internet Information Services (IIS) Manager**, click **Default Web Site**.</span></span>  
  
2.  <span data-ttu-id="4cee7-164">No painel do meio, clique duas vezes em **Autenticação**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-164">In the middle pane, double-click **Authentication**.</span></span>  
  
3.  <span data-ttu-id="4cee7-165">Clique com o botão direito do mouse em Autenticação Anônima e escolha Desabilitar.</span><span class="sxs-lookup"><span data-stu-id="4cee7-165">Right-click Anonymous Authentication, and then choose Disable.</span></span>  
  
4.  <span data-ttu-id="4cee7-166">Clique com o botão direito do mouse em Autenticação Básica e escolha Habilitar.</span><span class="sxs-lookup"><span data-stu-id="4cee7-166">Right-click Basic Authentication, and then choose Enable.</span></span>  
  
## <a name="configuring-secure-sockets-layer"></a><span data-ttu-id="4cee7-167">Configurando o protocolo SSL</span><span class="sxs-lookup"><span data-stu-id="4cee7-167">Configuring Secure Sockets Layer</span></span>  
 <span data-ttu-id="4cee7-168">Para configurar o SSL, especifique um certificado a ser usado pelo computador que está executando o IIS.</span><span class="sxs-lookup"><span data-stu-id="4cee7-168">To configure SSL, specify a certificate to be used by the computer running IIS.</span></span> <span data-ttu-id="4cee7-169">A sincronização da Web para replicação de mesclagem dá suporte ao uso de certificados de servidor, mas não de certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="4cee7-169">Web synchronization for merge replication supports using server certificates, but not client certificates.</span></span> <span data-ttu-id="4cee7-170">Para configurar o IIS para implantação, você deve obter primeiro um certificado de uma CA (autoridade de certificação).</span><span class="sxs-lookup"><span data-stu-id="4cee7-170">To configure IIS for deployment, you must first obtain a certificate from a certification authority (CA).</span></span> <span data-ttu-id="4cee7-171">Para obter mais informações sobre certificados, consulte a documentação do IIS.</span><span class="sxs-lookup"><span data-stu-id="4cee7-171">For more information about certificates, see the IIS documentation.</span></span>  
  
 <span data-ttu-id="4cee7-172">Depois de instalar o certificado, você deve associar o certificado ao site da Web que é usado pela sincronização da Web.</span><span class="sxs-lookup"><span data-stu-id="4cee7-172">After you install the certificate, you must associate the certificate with the Web site that is used by Web synchronization.</span></span> <span data-ttu-id="4cee7-173">Para desenvolvimento e testes, você pode especificar um certificado autoassinado.</span><span class="sxs-lookup"><span data-stu-id="4cee7-173">For development and testing, you can specify a self-signed certificate.</span></span> <span data-ttu-id="4cee7-174">O IIS 7 pode criar um certificado para você e registrá-lo em seu computador.</span><span class="sxs-lookup"><span data-stu-id="4cee7-174">IIS 7 can create a certificate for you and register it on your computer.</span></span>  
  
 <span data-ttu-id="4cee7-175">A diferença entre a implantação para produção e os procedimentos fornecidos aqui é que, em produção e em testes de pré-produção, você usa um certificado emitido por uma CA em vez de um certificado autoassinado.</span><span class="sxs-lookup"><span data-stu-id="4cee7-175">The difference between deploying for production and the procedures given here is that in production and pre-production testing, you would use a certificate issued by a CA instead of a self-signed certificate.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4cee7-176">Um certificado autoassinado não é recomendável para uma instalação de produção.</span><span class="sxs-lookup"><span data-stu-id="4cee7-176">A self-signed certificate is not recommended for a production installation.</span></span> <span data-ttu-id="4cee7-177">Certificados autoassinados não são seguros.</span><span class="sxs-lookup"><span data-stu-id="4cee7-177">Self-signed certificates are not secure.</span></span> <span data-ttu-id="4cee7-178">Use certificados autoassinados apenas para desenvolvimento e testes.</span><span class="sxs-lookup"><span data-stu-id="4cee7-178">Use self-signed certificates for development and testing only.</span></span>  
  
 <span data-ttu-id="4cee7-179">Para configurar o SSL, você executará as etapas a seguir:</span><span class="sxs-lookup"><span data-stu-id="4cee7-179">To configure SSL, you will perform the following steps:</span></span>  
  
1.  <span data-ttu-id="4cee7-180">Configure o site para exigir o SSL e ignorar certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="4cee7-180">Configure the Web site to require SSL and ignore client certificates.</span></span>  
  
2.  <span data-ttu-id="4cee7-181">Obtenha um certificado de uma CA ou crie um certificado autoassinado.</span><span class="sxs-lookup"><span data-stu-id="4cee7-181">Obtain a certificate from a CA or create a self-signed certificate.</span></span>  
  
3.  <span data-ttu-id="4cee7-182">Associe o certificado ao site de replicação.</span><span class="sxs-lookup"><span data-stu-id="4cee7-182">Bind the certificate to the replication Web site.</span></span>  
  
#### <a name="to-require-ssl-security-for-a-web-site"></a><span data-ttu-id="4cee7-183">Para exigir segurança de SSL para um site</span><span class="sxs-lookup"><span data-stu-id="4cee7-183">To require SSL security for a Web site</span></span>  
  
1.  <span data-ttu-id="4cee7-184">No **Gerenciador dos Serviços de Informações da Internet (IIS)** , expanda o nó do servidor local e clique no **Site Padrão** (ou no seu site de sincronização da Web se ele for diferente do site padrão).</span><span class="sxs-lookup"><span data-stu-id="4cee7-184">In **Internet Information Services (IIS) Manager**, expand the local server node, and then click the **Default Web Site** (or your Web synchronization site if it is different from the default Web site).</span></span>  
  
2.  <span data-ttu-id="4cee7-185">No painel do meio, clique duas vezes em **Configurações de SSL**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-185">In the middle pane, double-click **SSL Settings**.</span></span>  
  
3.  <span data-ttu-id="4cee7-186">Marque a opção **Exigir SSL** .</span><span class="sxs-lookup"><span data-stu-id="4cee7-186">Check the **Require SSL** option.</span></span> <span data-ttu-id="4cee7-187">Em **Certificados de cliente**, verifique se o botão **Ignorar** está selecionado.</span><span class="sxs-lookup"><span data-stu-id="4cee7-187">Under **Client certificates**, verify that the **Ignore** button is selected.</span></span>  
  
#### <a name="to-create-a-self-signed-certificate-for-testing"></a><span data-ttu-id="4cee7-188">Para criar um certificado autoassinado para testes</span><span class="sxs-lookup"><span data-stu-id="4cee7-188">To create a self-signed certificate for testing</span></span>  
  
1.  <span data-ttu-id="4cee7-189">Em **Gerenciador dos Serviços de Informações da Internet (IIS)** , clique no nó do servidor local e, em seguida, no painel central, clique duas vezes em **Certificados de Servidor**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-189">In **Internet Information Services (IIS) Manager**, click the local server node, and then in the center pane, double-click on **Server Certificates**.</span></span>  
  
2.  <span data-ttu-id="4cee7-190">No painel **Ações** , clique em **Criar Certificado Autoassinado**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-190">In the **Actions** pane, click **Create Self-Signed Certificate**.</span></span>  
  
3.  <span data-ttu-id="4cee7-191">Na caixa de diálogo **Criar Certificado Autoassinado** , digite um nome para o certificado e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-191">In the **Create Self-Signed Certificate** dialog box, enter a name for the certificate, and then click **OK**.</span></span>  
  
###### <a name="to-bind-a-certificate-to-a-web-site"></a><span data-ttu-id="4cee7-192">Para associar um certificado a um site</span><span class="sxs-lookup"><span data-stu-id="4cee7-192">To bind a certificate to a Web site</span></span>  
  
1.  <span data-ttu-id="4cee7-193">No painel **Conexões** , clique no **Site Padrão** (ou no seu site de sincronização da Web, se ele for diferente do site padrão).</span><span class="sxs-lookup"><span data-stu-id="4cee7-193">In the **Connections** pane, click the **Default Web Site** (or your Web synchronization site, if it is different from the default Web site).</span></span>  
  
2.  <span data-ttu-id="4cee7-194">No painel **Ações** , clique em **Associações**e, em seguida, em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-194">In the **Actions** pane, click **Bindings**, and then click **Add**.</span></span> <span data-ttu-id="4cee7-195">A caixa de diálogo **Adicionar Ligação do Site** será exibida.</span><span class="sxs-lookup"><span data-stu-id="4cee7-195">The **Add Site Binding** dialog box will appear.</span></span>  
  
3.  <span data-ttu-id="4cee7-196">Na lista suspensa **Tipo** , selecione **https**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-196">From the **Type** drop-down list, select **https**.</span></span> <span data-ttu-id="4cee7-197">Deixe as configurações padrão de **Endereço IP** e **Porta**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-197">Leave the default settings for **IP address** and **Port**.</span></span>  
  
4.  <span data-ttu-id="4cee7-198">Na lista suspensa **Certificado SSL** , selecione o certificado criado em "Para criar um certificado autoassinado para testes", clique em **OK**e, em seguida em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-198">From the **SSL certificate** drop-down list, select the certificate created in "To create a self-signed certificate for testing," click **OK**, and then click **Close**.</span></span>  
  
###### <a name="to-test-the-certificate"></a><span data-ttu-id="4cee7-199">Para testar o certificado</span><span class="sxs-lookup"><span data-stu-id="4cee7-199">To test the certificate</span></span>  
  
1.  <span data-ttu-id="4cee7-200">No **Noternet Noformation Services (IIS) Manager**, clique em **Site Padrão.**</span><span class="sxs-lookup"><span data-stu-id="4cee7-200">In **Internet Information Services (IIS) Manager**, click **Default Web Site.**</span></span>  
  
2.  <span data-ttu-id="4cee7-201">No painel **Ações**, clique em **Procurar \*:443(https)** .</span><span class="sxs-lookup"><span data-stu-id="4cee7-201">From the **Actions** pane, click **Browse \*:443(https)**.</span></span>  
  
3.  <span data-ttu-id="4cee7-202">O Internet Explorer será aberto e exibirá uma mensagem informando que "Há um problema com o certificado de segurança deste site".</span><span class="sxs-lookup"><span data-stu-id="4cee7-202">Internet Explorer will open and display a message that "There is a problem with this website's security certificate."</span></span> <span data-ttu-id="4cee7-203">Este aviso informa que o certificado associado não foi emitido por uma CA reconhecida e talvez não seja confiável.</span><span class="sxs-lookup"><span data-stu-id="4cee7-203">This warning tells you that the associated certificate was not issued by a recognized CA and might not be trustworthy.</span></span> <span data-ttu-id="4cee7-204">Esse é um aviso esperado, portanto, clique em **Continuar neste site (não recomendado)** .</span><span class="sxs-lookup"><span data-stu-id="4cee7-204">This is an expected warning, so click **Continue to this website (not recommended)**.</span></span>  
  
4.  <span data-ttu-id="4cee7-205">Se for solicitado a **Conectar ao host local**, digite um nome de usuário e senha para continuar.</span><span class="sxs-lookup"><span data-stu-id="4cee7-205">If you are prompted to **Connect to localhost**, enter a user name and password to proceed.</span></span> <span data-ttu-id="4cee7-206">Você deve ver a página padrão do site.</span><span class="sxs-lookup"><span data-stu-id="4cee7-206">You should see the default page for the Web site.</span></span>  
  
## <a name="setting-permissions-for-the-sql-server-replication-listener"></a><span data-ttu-id="4cee7-207">Definindo permissões para o SQL Server Replication Listener</span><span class="sxs-lookup"><span data-stu-id="4cee7-207">Setting Permissions for the SQL Server Replication Listener</span></span>  
 <span data-ttu-id="4cee7-208">Quando um computador assinante se conecta ao computador que está executando o IIS, o assinante é autenticado usando o tipo de autenticação especificado quando o IIS foi configurado.</span><span class="sxs-lookup"><span data-stu-id="4cee7-208">When a subscriber computer connects to the computer running IIS, the subscriber is authenticated by using the type of authentication specified when you configured IIS.</span></span> <span data-ttu-id="4cee7-209">Depois de autenticar o assinante, o IIS verifica se o assinante está autorizado a chamar a replicação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4cee7-209">After IIS authenticates the subscriber, IIS checks whether the subscriber is authorized to invoke [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication.</span></span> <span data-ttu-id="4cee7-210">Você controla os usuários que podem invocar a replicação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] definindo as permissões para replisapi.dll.</span><span class="sxs-lookup"><span data-stu-id="4cee7-210">You control the users that can invoke [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication by setting permissions for replisapi.dll.</span></span> <span data-ttu-id="4cee7-211">É necessário configurar corretamente as permissões para impedir acesso não autorizado à replicação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4cee7-211">Properly configuring permissions is necessary to prevent unauthorized access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication.</span></span>  
  
 <span data-ttu-id="4cee7-212">Para configurar as permissões mínimas para a conta sob a qual o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener é executado, realize o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="4cee7-212">To configure the minimum permissions for the account under which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Replication Listener runs, complete the following procedure.</span></span> <span data-ttu-id="4cee7-213">As etapas do procedimento a seguir se aplicam ao [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Server 2008 que está executando o IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="4cee7-213">The steps in the following procedure apply to [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Server 2008 running IIS 7.0.</span></span>  
  
 <span data-ttu-id="4cee7-214">Além de realizar as etapas a seguir, certifique-se de que os logons necessários estão na lista de acesso à publicação (PAL).</span><span class="sxs-lookup"><span data-stu-id="4cee7-214">In addition to performing the following steps, make sure that the required logins are in the publication access list (PAL).</span></span> <span data-ttu-id="4cee7-215">Para obter mais informações sobre a PAL, consulte [Secure the Publisher](security/secure-the-publisher.md) (Proteger o publicador).</span><span class="sxs-lookup"><span data-stu-id="4cee7-215">For more information about the PAL, see [Secure the Publisher](security/secure-the-publisher.md).</span></span>  
  
 <span data-ttu-id="4cee7-216">**Importante** a conta criada nesta seção é a conta que se conectará ao Publicador e ao Distribuidor durante a sincronização.</span><span class="sxs-lookup"><span data-stu-id="4cee7-216">**Important** The account created in this section is the account that will connect to the Publisher and Distributor during synchronization.</span></span> <span data-ttu-id="4cee7-217">Essa conta deve ser adicionada como uma conta de logon do SQL no servidor de distribuição e de publicação.</span><span class="sxs-lookup"><span data-stu-id="4cee7-217">This account must be added as a SQL Login account on the distribution and publication server.</span></span>  
  
 <span data-ttu-id="4cee7-218">A conta usada para o SQL Server Replication Listener deve ter permissões conforme descrito no tópico Segurança do Agente de Mesclagem, na seção "Conectar-se ao Publicador ou ao Distribuidor".</span><span class="sxs-lookup"><span data-stu-id="4cee7-218">The account used for the SQL Server Replication Listener must have permissions as described in the Merge Agent Security topic, in the "Connect to the Publisher or Distributor" section.</span></span>  
  
 <span data-ttu-id="4cee7-219">Em resumo, a conta deve:</span><span class="sxs-lookup"><span data-stu-id="4cee7-219">In summary, the account must:</span></span>  
  
-   <span data-ttu-id="4cee7-220">Ser um membro da lista de acesso à publicação (PAL).</span><span class="sxs-lookup"><span data-stu-id="4cee7-220">Be a member of the Publication Access List (PAL).</span></span>  
  
-   <span data-ttu-id="4cee7-221">Ser mapeada para um logon associado a um usuário no banco de dados de publicação.</span><span class="sxs-lookup"><span data-stu-id="4cee7-221">Be mapped to a login associated with a user in the publication database.</span></span>  
  
-   <span data-ttu-id="4cee7-222">Ser mapeada para um logon associado a um usuário no banco de dados de distribuição.</span><span class="sxs-lookup"><span data-stu-id="4cee7-222">Be mapped to a login associated with a user in the distribution database.</span></span>  
  
-   <span data-ttu-id="4cee7-223">Ter permissões de Leitura no compartilhamento de instantâneos.</span><span class="sxs-lookup"><span data-stu-id="4cee7-223">Have Read permissions on the snapshot share.</span></span>  
  
#### <a name="to-configure-the-account-and-permissions"></a><span data-ttu-id="4cee7-224">Para configurar a conta e as permissões</span><span class="sxs-lookup"><span data-stu-id="4cee7-224">To configure the account and permissions</span></span>  
  
1.  <span data-ttu-id="4cee7-225">Crie uma conta local no computador que está executando o IIS:</span><span class="sxs-lookup"><span data-stu-id="4cee7-225">Create a local account on the computer running IIS:</span></span>  
  
    1.  <span data-ttu-id="4cee7-226">Abra o **Server Manager**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-226">Open **Server Manager**.</span></span> <span data-ttu-id="4cee7-227">No menu Iniciar, clique com o botão direito do mouse em **Computador**e clique em **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-227">From the Start menu, right-click **Computer**, and then click **Manage**.</span></span>  
  
    2.  <span data-ttu-id="4cee7-228">No **Server Manager**, expanda **Configuração**e, em seguida, expanda **Usuários Locais e Grupos**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-228">In **Server Manager**, expand **Configuration**, and then expand **Local Users and Groups**.</span></span>  
  
    3.  <span data-ttu-id="4cee7-229">Clique com o botão direito do mouse em **Usuários**e depois clique em **Novo Usuário**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-229">Right-click **Users**, and then click **New User**.</span></span>  
  
    4.  <span data-ttu-id="4cee7-230">Digite um nome de usuário e uma senha forte.</span><span class="sxs-lookup"><span data-stu-id="4cee7-230">Enter a user name and a strong password.</span></span> <span data-ttu-id="4cee7-231">Limpe **O usuário deve alterar a senha no próximo logon**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-231">Clear **User must change password at next logon**.</span></span>  
  
    5.  <span data-ttu-id="4cee7-232">Clique em **Criar**e depois em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-232">Click **Create**, and then click **Close**.</span></span>  
  
2.  <span data-ttu-id="4cee7-233">Adicione a conta ao grupo IIS_IUSRS:</span><span class="sxs-lookup"><span data-stu-id="4cee7-233">Add the account to the IIS_IUSRS group:</span></span>  
  
    1.  <span data-ttu-id="4cee7-234">No **Server Manager**, expanda **Configuração**e, em seguida, expanda **Usuários Locais e Grupos**e clique em **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-234">In **Server Manager**, expand **Configuration**, expand **Local Users and Groups**, and then click **Groups**.</span></span>  
  
    2.  <span data-ttu-id="4cee7-235">Clique com o botão direito do mouse em **IIS_IUSRS**e, em seguida, clique em **Adicionar ao Grupo**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-235">Right-click **IIS_IUSRS**, and then click **Add to Group**.</span></span>  
  
    3.  <span data-ttu-id="4cee7-236">Na caixa de diálogo **Propriedades de IIS_IUSRS** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-236">In the **IIS_IUSRS Properties** dialog box, click **Add**.</span></span>  
  
    4.  <span data-ttu-id="4cee7-237">Na caixa de diálogo **Selecionar Usuários, Computadores ou Grupos** , adicione a conta criada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="4cee7-237">In the **Select Users, Computers, or Groups** dialog box, add the account created in step 1.</span></span>  
  
    5.  <span data-ttu-id="4cee7-238">Verifique se **Deste local** exibe o nome do computador local (não um domínio).</span><span class="sxs-lookup"><span data-stu-id="4cee7-238">Verify that **From this location** displays the name of the local computer (not a domain).</span></span> <span data-ttu-id="4cee7-239">Se esse campo não exibir o nome do computador local, clique em **Locais**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-239">If this field does not display the local computer name, click **Locations**.</span></span> <span data-ttu-id="4cee7-240">Na caixa de diálogo **Locais** , selecione o computador local e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-240">In the **Locations** dialog box, select the local computer, and then click **OK**.</span></span>  
  
    6.  <span data-ttu-id="4cee7-241">Nas caixas de diálogo **Selecionar Usuários** e **Propriedades de IIS_IUSRS** , clique em**OK**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-241">In the **Select Users** dialog box and the **IIS_IUSRS Properties** dialog box, click**OK**.</span></span>  
  
3.  <span data-ttu-id="4cee7-242">Conceda as permissões mínimas de conta na pasta que contém replisapi.dll:</span><span class="sxs-lookup"><span data-stu-id="4cee7-242">Grant minimum account permissions on the folder that contains replisapi.dll:</span></span>  
  
    1.  <span data-ttu-id="4cee7-243">No Windows Explorer, clique com o botão direito do mouse na pasta que você criou para replisapi.dll e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-243">In Windows Explorer, right-click the folder that you created for replisapi.dll, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="4cee7-244">Na guia **Segurança** , clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-244">On the **Security** tab, click **Edit**.</span></span>  
  
    3.  <span data-ttu-id="4cee7-245">Na caixa de diálogo **Permissões para \<foldername>** , clique em **Adicionar** para adicionar a conta que você criou na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="4cee7-245">In the **Permissions for \<foldername>** dialog box, click **Add** to add the account that you created in step 1.</span></span>  
  
    4.  <span data-ttu-id="4cee7-246">Verifique se **Deste local** exibe o nome do computador local (não um domínio).</span><span class="sxs-lookup"><span data-stu-id="4cee7-246">Verify that **From this location** displays the name of the local computer (not a domain).</span></span> <span data-ttu-id="4cee7-247">Se esse campo não exibir o nome do computador local, clique em **Locais**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-247">If this field does not display the local computer name, click **Locations**.</span></span> <span data-ttu-id="4cee7-248">Na caixa de diálogo **Locais** , selecione o computador local e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-248">In the **Locations** dialog box, select the local computer, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="4cee7-249">Verifique se a conta tem permissão apenas para **Ler**, **Ler e Executar** e **Listar Conteúdo da Pasta**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-249">Verify that the account is granted only **Read**, **Read & Execute**, and **List Folder Contents** permissions.</span></span>  
  
    6.  <span data-ttu-id="4cee7-250">Selecione qualquer usuário ou grupo que não requeira acesso ao diretório, clique em **Remover**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-250">Select any users or groups that do not require access to the directory, click **Remove**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="4cee7-251">Crie um pool de aplicativos no **Gerenciador dos Serviços de Informação de Internet (IIS)** :</span><span class="sxs-lookup"><span data-stu-id="4cee7-251">Create an application pool in **Internet Information Services (IIS) Manager**:</span></span>  
  
    1.  <span data-ttu-id="4cee7-252">No **Gerenciador dos Serviços de Informações da Internet (IIS)** , no painel **Conexões** , expanda o nó do servidor local.</span><span class="sxs-lookup"><span data-stu-id="4cee7-252">In **Internet Information Services (IIS) Manager**, in the **Connections** pane, expand the local server node.</span></span>  
  
    2.  <span data-ttu-id="4cee7-253">Clique com o botão direito do mouse em **Pools de Aplicativos**e clique em **Adicionar Pool de Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-253">Right-click **Application Pools**, and then click **Add Application Pool**.</span></span>  
  
    3.  <span data-ttu-id="4cee7-254">Digite um nome para o pool de aplicativos, deixe os valores padrão para as pastas restantes e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-254">Enter a name for the application pool, leave the default values for the remaining fields, and then click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4cee7-255">Se você prevê que terá mais de dois clientes de sincronização simultâneos, poderá criar um ambiente Web.</span><span class="sxs-lookup"><span data-stu-id="4cee7-255">If you anticipate having more than two concurrent synchronization clients, you might want to create a web garden.</span></span> <span data-ttu-id="4cee7-256">Para obter mais informações, consulte “Criando um Ambiente Web” em [Configure a sincronização da Web](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="4cee7-256">For more information, see "Creating a Web Garden" in [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
5.  <span data-ttu-id="4cee7-257">Associe a conta com o pool de aplicativos:</span><span class="sxs-lookup"><span data-stu-id="4cee7-257">Associate the account with the application pool:</span></span>  
  
    1.  <span data-ttu-id="4cee7-258">No **Gerenciador dos Serviços de Informações da Internet (IIS)** , expanda o nó do servidor local e clique em **Pool de Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-258">In **Internet Information Services (IIS) Manager**, expand the local server node, and then click on **Application Pools**.</span></span>  
  
    2.  <span data-ttu-id="4cee7-259">Clique com o botão direito do mouse no pool de aplicativos que você criou e clique em **Definir Padrões do Pool de Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-259">Right-click the application pool that you created, and then click **Set Application Pool Defaults**.</span></span>  
  
    3.  <span data-ttu-id="4cee7-260">Na caixa de diálogo **Padrões do Pool de Aplicativos** , role até a seção **Modelo de Processo** e clique no campo **Identidade** .</span><span class="sxs-lookup"><span data-stu-id="4cee7-260">In the **Application Pool Defaults** dialog box, scroll down to the **Process Model** section, and then click the **Identity** field.</span></span>  
  
    4.  <span data-ttu-id="4cee7-261">Clique no botão de elipse à direita da linha **Identidade** .</span><span class="sxs-lookup"><span data-stu-id="4cee7-261">Click the ellipsis button on the right side of the **Identity** row.</span></span>  
  
    5.  <span data-ttu-id="4cee7-262">Clique no botão de opção **Conta Personalizada** e clique em **Definir**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-262">Click the **Custom Account** radio button, and then click **Set**.</span></span>  
  
    6.  <span data-ttu-id="4cee7-263">Nos campos **Nome de usuário** e **Senha** , digite a conta e a senha que foram criadas na etapa 1 e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-263">In the **User name** and **Password** fields, enter the account and password that were created in step 1, and then click **OK**.</span></span>  
  
    7.  <span data-ttu-id="4cee7-264">Clique em **OK** para fechar a caixa de diálogo **Identidade do Pool de Aplicativos** e clique em **OK** novamente para fechar a caixa de diálogo **Padrões do Pool de Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-264">Click **OK** to close the **Application Pool Identity** dialog box, and then click **OK** again to close the **Application Pool Defaults**dialog box.</span></span>  
  
6.  <span data-ttu-id="4cee7-265">Associe o pool de aplicativos ao site de replicação:</span><span class="sxs-lookup"><span data-stu-id="4cee7-265">Associate the application pool with the replication Web site:</span></span>  
  
    1.  <span data-ttu-id="4cee7-266">Em **Gerenciador dos Serviços de Informações da Internet (IIS)** , expanda o nó do servidor local e clique no **Site Padrão** (ou no seu site de sincronização da Web se ele for diferente do site padrão).</span><span class="sxs-lookup"><span data-stu-id="4cee7-266">In **Internet Information Services (IIS) Manager**, expand the local server node, and then click on the **Default Web Site** (or your Web synchronization site if it is different from the default Web site).</span></span>  
  
    2.  <span data-ttu-id="4cee7-267">No painel **Ações** , sob **Gerenciar Site**, clique em **Configurações Avançadas**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-267">In the **Actions** pane, under **Manage Web Site**, click **Advanced Settings**.</span></span>  
  
    3.  <span data-ttu-id="4cee7-268">Na caixa de diálogo **Configurações Avançadas** , clique no botão de elipse à direita de **Pool de Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-268">In the **Advanced Settings** dialog box, click on the ellipsis button to the right of **Application Pool**.</span></span>  
  
    4.  <span data-ttu-id="4cee7-269">Na lista suspensa **Pool de aplicativos** , selecione o pool de aplicativos que você criou na etapa 4 e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-269">From the **Application pool** drop-down list, select the application pool you created in step 4, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="4cee7-270">Clique em **OK** novamente para fechar as Configurações Avançadas.</span><span class="sxs-lookup"><span data-stu-id="4cee7-270">Click **OK** again to close Advanced Settings.</span></span>  
  
## <a name="testing-the-connection-to-replisapidll"></a><span data-ttu-id="4cee7-271">Testando a conexão com replisapi.dll</span><span class="sxs-lookup"><span data-stu-id="4cee7-271">Testing the Connection to replisapi.dll</span></span>  
 <span data-ttu-id="4cee7-272">Execute a sincronização da Web em modo de diagnóstico para testar a conexão com o computador que está executando o IIS e certificar-se de que o certificado SSL está instalado adequadamente.</span><span class="sxs-lookup"><span data-stu-id="4cee7-272">Run Web synchronization in diagnostic mode to test the connection to the computer running IIS and to make sure that the Secure Sockets Layer (SSL) certificate is properly installed.</span></span> <span data-ttu-id="4cee7-273">Para executar a sincronização da Web em modo diagnóstico, você deve ser um administrador no computador que executa o IIS.</span><span class="sxs-lookup"><span data-stu-id="4cee7-273">To run Web synchronization in diagnostic mode, you must be an administrator on the computer running IIS.</span></span>  
  
#### <a name="to-test-the-connection-to-replisapidll"></a><span data-ttu-id="4cee7-274">Para testar a conexão com replisapi.dll</span><span class="sxs-lookup"><span data-stu-id="4cee7-274">To test the connection to replisapi.dll</span></span>  
  
1.  <span data-ttu-id="4cee7-275">Certifique-se de que as configurações de rede local (LAN) no Assinante estão corretas:</span><span class="sxs-lookup"><span data-stu-id="4cee7-275">Make sure that local area network (LAN) settings at the Subscriber are correct:</span></span>  
  
    1.  <span data-ttu-id="4cee7-276">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer, no menu **Ferramentas** , clique em **Opções da Internet**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-276">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer, on the **Tools** menu, click **Internet Options**.</span></span>  
  
    2.  <span data-ttu-id="4cee7-277">Na guia **Conexões** , clique em **Configurações da LAN**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-277">On the **Connections** tab, click **LAN Settings**.</span></span>  
  
    3.  <span data-ttu-id="4cee7-278">Se um servidor proxy não for usado na LAN, desmarque **Detectar Automaticamente as Configurações** e **Usar um servidor proxy para a rede local**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-278">If a proxy server is not used on the LAN, clear **Automatically Detect Settings** and **Use a proxy server for your LAN**.</span></span>  
  
    4.  <span data-ttu-id="4cee7-279">Se um servidor proxy for usado, clique em **Usar um servidor proxy para a rede local** e **Ignorar servidor proxy para endereços locais**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-279">If a proxy server is used, click **Use a proxy server for your LAN** and **Bypass proxy server for local addresses**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="4cee7-280">No Assinante, no Internet Explorer, conecte-se ao servidor em modo de diagnóstico adicionando `?diag` ao endereço para o replisapi.dll.</span><span class="sxs-lookup"><span data-stu-id="4cee7-280">At the Subscriber, in Internet Explorer, connect to the server in diagnostic mode by appending `?diag` to the address for the replisapi.dll.</span></span> <span data-ttu-id="4cee7-281">Por exemplo: `https://server.domain.com/directory/replisapi.dll?diag`.</span><span class="sxs-lookup"><span data-stu-id="4cee7-281">For example: `https://server.domain.com/directory/replisapi.dll?diag`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4cee7-282">No exemplo anterior, **server.domain.com** deve ser substituído pelo nome exato de **Emitido para** listado na seção **Certificados de Servidor** no Gerenciador do IIS.</span><span class="sxs-lookup"><span data-stu-id="4cee7-282">In the example above, **server.domain.com** should be replaced with the exact **Issued To** name listed under the **Server Certificates** section in IIS Manager.</span></span>  
  
3.  <span data-ttu-id="4cee7-283">Se o certificado especificado para o IIS não for reconhecido pelo sistema operacional Windows, a caixa de diálogo **Alerta da Segurança** será exibida.</span><span class="sxs-lookup"><span data-stu-id="4cee7-283">If the certificate that you specified for IIS is not recognized by the Windows operating system, the **Security Alert** dialog box appears.</span></span> <span data-ttu-id="4cee7-284">Esse alerta pode ocorrer porque o certificado é um certificado de teste ou porque o certificado foi emitido por uma autoridade de certificação (CA) que não é reconhecida pelo Windows.</span><span class="sxs-lookup"><span data-stu-id="4cee7-284">This alert might occur because the certificate is a test certificate or the certificate was issued by a certification authority (CA) that Windows does not recognize.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4cee7-285">Se essa caixa de diálogo não aparecer, certifique-se de que o certificado para o servidor que você está acessando foi adicionado ao repositório de certificados no Assinante como um certificado confiável.</span><span class="sxs-lookup"><span data-stu-id="4cee7-285">If this dialog box does not appear, make sure that the certificate for the server that you are accessing has been added to the certificate store at the Subscriber as a trusted certificate.</span></span> <span data-ttu-id="4cee7-286">Para obter mais informações sobre exportação de certificados, consulte a documentação do IIS.</span><span class="sxs-lookup"><span data-stu-id="4cee7-286">For more information about exporting certificates, see the IIS documentation.</span></span>  
  
    1.  <span data-ttu-id="4cee7-287">Na caixa de diálogo **Alerta de Segurança** , clique em **Exibir Certificado**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-287">In the **Security Alert** dialog box, click **View Certificate**.</span></span>  
  
    2.  <span data-ttu-id="4cee7-288">Na caixa de diálogo **Certificado** , na guia **Geral** , clique em **Instalar Certificado**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-288">In the **Certificate** dialog box, on the **General** tab, click **Install Certificate**.</span></span>  
  
    3.  <span data-ttu-id="4cee7-289">Conclua o Assistente para Importação de Certificados, aceitando os padrões.</span><span class="sxs-lookup"><span data-stu-id="4cee7-289">Complete the Certificate Import Wizard, accepting the defaults.</span></span>  
  
    4.  <span data-ttu-id="4cee7-290">Na caixa de diálogo **Aviso de Segurança** , clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-290">In the **Security Warning** dialog box, click **Yes**.</span></span>  
  
    5.  <span data-ttu-id="4cee7-291">Na caixa de diálogo de confirmação do Assistente para Importação de Certificados, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-291">In the Certificate Import Wizard confirmation dialog box, click **OK**.</span></span>  
  
    6.  <span data-ttu-id="4cee7-292">Feche a caixa de diálogo **Certificado** .</span><span class="sxs-lookup"><span data-stu-id="4cee7-292">Close the **Certificate** dialog box.</span></span>  
  
    7.  <span data-ttu-id="4cee7-293">Na caixa de diálogo **Alerta de Segurança** , clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-293">In the **Security Alert** dialog box, click **Yes**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4cee7-294">Os certificados serão instalados para os usuários.</span><span class="sxs-lookup"><span data-stu-id="4cee7-294">Certificates are installed for users.</span></span> <span data-ttu-id="4cee7-295">Esse processo deve ser executado para cada usuário que sincronizará com o IIS.</span><span class="sxs-lookup"><span data-stu-id="4cee7-295">This process must be performed for each user that will synchronize with IIS.</span></span>  
  
4.  <span data-ttu-id="4cee7-296">Na caixa de diálogo **Conectar-se ao \<ServerName>** , especifique o logon e a senha que o Agente de Mesclagem usará para se conectar ao IIS.</span><span class="sxs-lookup"><span data-stu-id="4cee7-296">In the **Connect to \<ServerName>** dialog box, specify the login and password that the Merge Agent will use to connect to IIS.</span></span> <span data-ttu-id="4cee7-297">Essas credenciais também serão especificadas no Assistente para Nova Assinatura.</span><span class="sxs-lookup"><span data-stu-id="4cee7-297">These credentials will also be specified in the New Subscription Wizard.</span></span>  
  
5.  <span data-ttu-id="4cee7-298">Na janela do Internet Explorer chamada **Informação diagnóstica do SQL Websync**, verifique se o valor em cada coluna **Status** na página é **ÊXITO**.</span><span class="sxs-lookup"><span data-stu-id="4cee7-298">In the Internet Explorer window called **SQL Websync diagnostic information**, verify that the value in each **Status** column on the page is **SUCCESS**.</span></span>  
  
6.  <span data-ttu-id="4cee7-299">Certifique-se de que o certificado está instalado corretamente no Assinante:</span><span class="sxs-lookup"><span data-stu-id="4cee7-299">Make sure that the certificate is installed correctly on the Subscriber:</span></span>  
  
    1.  <span data-ttu-id="4cee7-300">Feche e depois reabra o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="4cee7-300">Close and then reopen Internet Explorer.</span></span>  
  
    2.  <span data-ttu-id="4cee7-301">Conecte ao servidor em modo diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="4cee7-301">Connect to the server in diagnostic mode.</span></span> <span data-ttu-id="4cee7-302">Se o certificado estiver instalado corretamente, a caixa de diálogo **Alerta de Segurança** não aparecerá.</span><span class="sxs-lookup"><span data-stu-id="4cee7-302">If the certificate is installed properly, the **Security Alert** dialog box will not appear.</span></span> <span data-ttu-id="4cee7-303">Se a caixa de diálogo aparecer, o Merge Agent apresentará falha quando tentar se conectar ao computador que está executando o IIS.</span><span class="sxs-lookup"><span data-stu-id="4cee7-303">If the dialog box appears, the Merge Agent will fail when it tries to connect to the computer that is running IIS.</span></span> <span data-ttu-id="4cee7-304">Você deve certificar-se de que o certificado para o servidor que você está acessando foi adicionado ao repositório de certificados no Assinante como um certificado confiável.</span><span class="sxs-lookup"><span data-stu-id="4cee7-304">You must make sure that the certificate for the server that you are accessing has been added to the certificate store at the Subscriber as a trusted certificate.</span></span> <span data-ttu-id="4cee7-305">Para obter mais informações sobre exportação de certificados, consulte a documentação do IIS.</span><span class="sxs-lookup"><span data-stu-id="4cee7-305">For more information about exporting certificates, see the IIS documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cee7-306">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4cee7-306">See Also</span></span>  
 <span data-ttu-id="4cee7-307">[Sincronização da Web para replicação de mesclagem](web-synchronization-for-merge-replication.md) </span><span class="sxs-lookup"><span data-stu-id="4cee7-307">[Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md) </span></span>  
 [<span data-ttu-id="4cee7-308">Configurar a Sincronização da Web</span><span class="sxs-lookup"><span data-stu-id="4cee7-308">Configure Web Synchronization</span></span>](configure-web-synchronization.md)  
  
  
