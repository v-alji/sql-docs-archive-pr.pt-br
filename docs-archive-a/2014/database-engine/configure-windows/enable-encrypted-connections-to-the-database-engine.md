---
title: Habilitar conexões criptografadas para o Mecanismo de Banco de Dados (SQL Server Configuration Manager) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- connections [SQL Server], encrypted
- SSL [SQL Server]
- Secure Sockets Layer (SSL)
- encryption [SQL Server], connections
- cryptography [SQL Server], connections
- certificates [SQL Server], installing
- requesting encrypted connections
- installing certificates
- security [SQL Server], encryption
ms.assetid: e1e55519-97ec-4404-81ef-881da3b42006
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e1653df929e3f8bc67158a0685ce07b8ba65de6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685267"
---
# <a name="enable-encrypted-connections-to-the-database-engine-sql-server-configuration-manager"></a><span data-ttu-id="f0a86-102">Habilitar conexões criptografadas no Mecanismo de Banco de Dados (SQL Server Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="f0a86-102">Enable Encrypted Connections to the Database Engine (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="f0a86-103">Este tópico descreve como habilitar conexões criptografadas para uma instância do [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] especificando um certificado para o [!INCLUDE[ssDE](../../includes/ssde-md.md)] usando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f0a86-103">This topic describes how to enable encrypted connections for an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] by specifying a certificate for the [!INCLUDE[ssDE](../../includes/ssde-md.md)] using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="f0a86-104">O computador servidor deve ter um certificado configurado e a máquina cliente deve estar configurada para confiar na autoridade raiz do certificado.</span><span class="sxs-lookup"><span data-stu-id="f0a86-104">The server computer must have a certificate provisioned, and the client machine must be set up to trust the certificate's root authority.</span></span> <span data-ttu-id="f0a86-105">Provisionamento é o processo de instalar um certificado importando-o para o Windows.</span><span class="sxs-lookup"><span data-stu-id="f0a86-105">Provisioning is the process of installing a certificate by importing it into Windows.</span></span>  
  
 <span data-ttu-id="f0a86-106">O certificado deve ser emitido para **Autenticação do Servidor**.</span><span class="sxs-lookup"><span data-stu-id="f0a86-106">The certificate must be issued for **Server Authentication**.</span></span> <span data-ttu-id="f0a86-107">O nome do certificado deve ser o FQDN (nome de domínio totalmente qualificado) do computador.</span><span class="sxs-lookup"><span data-stu-id="f0a86-107">The name of the certificate must be the fully qualified domain name (FQDN) of the computer.</span></span>  
  
 <span data-ttu-id="f0a86-108">Os certificados são armazenados localmente para os usuários no computador.</span><span class="sxs-lookup"><span data-stu-id="f0a86-108">Certificates are stored locally for the users on the computer.</span></span> <span data-ttu-id="f0a86-109">Para instalar um certificado para uso pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você deve estar executando o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager na mesma conta de usuário que o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , a menos que o serviço esteja sendo executado como LocalSystem, NetworkService ou LocalService. Neste caso você pode usar uma conta administrativa.</span><span class="sxs-lookup"><span data-stu-id="f0a86-109">To install a certificate for use by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must be running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager under the same user account as the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service unless the service is running as LocalSystem, NetworkService, or LocalService, in which case you may use an administrative account.</span></span>  
  
 <span data-ttu-id="f0a86-110">O cliente deve poder verificar a propriedade do certificado usado pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="f0a86-110">The client must be able to verify the ownership of the certificate used by the server.</span></span> <span data-ttu-id="f0a86-111">Se o cliente tiver o certificado de chave pública da autoridade de certificação que assinou o certificado de servidor, nenhuma outra configuração será necessária.</span><span class="sxs-lookup"><span data-stu-id="f0a86-111">If the client has the public key certificate of the certification authority that signed the server certificate, no further configuration is necessary.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="f0a86-112">Windows inclui os certificados de chave pública de muitas autoridades de certificação.</span><span class="sxs-lookup"><span data-stu-id="f0a86-112">Windows includes the public key certificates of many certification authorities.</span></span> <span data-ttu-id="f0a86-113">Se o certificado do servidor foi assinado por uma autoridade de certificação pública ou privada para a qual o cliente não tem o certificado de chave pública, será necessário instalar o certificado de chave pública da autoridade de certificação que assinou o certificado do servidor.</span><span class="sxs-lookup"><span data-stu-id="f0a86-113">If the server certificate was signed by a public or private certification authority for which the client does not have the public key certificate, you must install the public key certificate of the certification authority that signed the server certificate.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f0a86-114">Para usar critografia com um cluster de failover, você deve instalar o certificado de servidor com o nome DNS completamente qualificado do servidor virtual em todos os nós no cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="f0a86-114">To use encryption with a failover cluster, you must install the server certificate with the fully qualified DNS name of the virtual server on all nodes in the failover cluster.</span></span> <span data-ttu-id="f0a86-115">Por exemplo, se você tiver um cluster de dois nós, com nós chamados Test1. *\<your company>* . com e test2. *\<your company>* . com, e você tiver um servidor virtual chamado virtsql, será necessário instalar um certificado para Virtsql. *\<your company>* . com em ambos os nós.</span><span class="sxs-lookup"><span data-stu-id="f0a86-115">For example, if you have a two-node cluster, with nodes named test1.*\<your company>*.com and test2.*\<your company>*.com, and you have a virtual server named virtsql, you need to install a certificate for virtsql.*\<your company>*.com on both nodes.</span></span> <span data-ttu-id="f0a86-116">Você pode definir o valor da opção **ForceEncryption**como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f0a86-116">You can set the value of the **ForceEncryption**option to **Yes**.</span></span>  
  
 <span data-ttu-id="f0a86-117">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="f0a86-117">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f0a86-118">**Para habilitar conexões criptografadas:**</span><span class="sxs-lookup"><span data-stu-id="f0a86-118">**To enable encrypted connections:**</span></span>  
  
     [<span data-ttu-id="f0a86-119">Provisionar (instalar) um certificado no servidor</span><span class="sxs-lookup"><span data-stu-id="f0a86-119">Provision (install) a certificate on the server</span></span>](#Provision)  
  
     [<span data-ttu-id="f0a86-120">Exportar o certificado de servidor</span><span class="sxs-lookup"><span data-stu-id="f0a86-120">Export the server certificate</span></span>](#Export)  
  
     [<span data-ttu-id="f0a86-121">Configurar o servidor para aceitar conexões criptografadas</span><span class="sxs-lookup"><span data-stu-id="f0a86-121">Configure the server to accept encrypted connections</span></span>](#ConfigureServerConnections)  
  
     [<span data-ttu-id="f0a86-122">Configurar o cliente para solicitar conexões criptografadas</span><span class="sxs-lookup"><span data-stu-id="f0a86-122">Configure the client to request encrypted connections</span></span>](#ConfigureClientConnections)  
  
     [<span data-ttu-id="f0a86-123">Criptografar uma conexão do SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0a86-123">Encrypt a connection from SQL Server Management Studio</span></span>](#EncryptConnection)  
  
##  <a name="SSMSProcedure"></a>  
  
###  <a name="to-provision-install-a-certificate-on-the-server"></a><a name="Provision"></a> <span data-ttu-id="f0a86-124">Para instalar um certificado no servidor</span><span class="sxs-lookup"><span data-stu-id="f0a86-124">To provision (install) a certificate on the server</span></span>  
  
1.  <span data-ttu-id="f0a86-125">No menu **Iniciar** , clique em **executar**e, na caixa **abrir** , digite `MMC` e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0a86-125">On the **Start** menu, click **Run**, and in the **Open** box, type `MMC` and click **OK**.</span></span>  
  
2.  <span data-ttu-id="f0a86-126">No console do MMC, no menu **Arquivo** , clique em **Adicionar/Remover Snap-in**.</span><span class="sxs-lookup"><span data-stu-id="f0a86-126">In the MMC console, on the **File** menu, click **Add/Remove Snap-in**.</span></span>  
  
3.  <span data-ttu-id="f0a86-127">Na caixa de diálogo **Adicionar/Remover Snap-in** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="f0a86-127">In the **Add/Remove Snap-in** dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="f0a86-128">Na caixa de diálogo **Adicionar Snap-in Autônomo** , clique em **Certificados**e em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="f0a86-128">In the **Add Standalone Snap-in** dialog box, click **Certificates**, click **Add**.</span></span>  
  
5.  <span data-ttu-id="f0a86-129">Na caixa de diálogo **Snap-in de certificados** , clique em **Conta de computador**e em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="f0a86-129">In the **Certificates snap-in** dialog box, click **Computer account**, and then click **Finish**.</span></span>  
  
6.  <span data-ttu-id="f0a86-130">Na caixa de diálogo **Adicionar Snap-in Autônomo** , clique em **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="f0a86-130">In the **Add Standalone Snap-in** dialog box, click **Close.**</span></span>  
  
7.  <span data-ttu-id="f0a86-131">Na caixa de diálogo **Adicionar/Remover Snap-in** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0a86-131">In the **Add/Remove Snap-in** dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="f0a86-132">No snap-in de **Certificados** , expanda **Certificados**, expanda **Pessoal**, clique com o botão direito do mouse em **Certificados**, aponte para **Todas as Tarefas**e clique em **Importar**.</span><span class="sxs-lookup"><span data-stu-id="f0a86-132">In the **Certificates** snap-in, expand **Certificates**, expand **Personal**, and then right-click **Certificates**, point to **All Tasks**, and then click **Import**.</span></span>  
  
9. <span data-ttu-id="f0a86-133">Complete o **Assistente para Importação de Certificados**, para adicionar um certificado ao computador e feche o console MMC.</span><span class="sxs-lookup"><span data-stu-id="f0a86-133">Complete the **Certificate Import Wizard**, to add a certificate to the computer, and close the MMC console.</span></span> <span data-ttu-id="f0a86-134">Para obter mais informações sobre como adicionar um certificado a um computador, consulte sua documentação do Windows.</span><span class="sxs-lookup"><span data-stu-id="f0a86-134">For more information about adding a certificate to a computer, see your Windows documentation.</span></span>  
  
###  <a name="to-export-the-server-certificate"></a><a name="Export"></a> <span data-ttu-id="f0a86-135">Para exportar o certificado de servidor</span><span class="sxs-lookup"><span data-stu-id="f0a86-135">To export the server certificate</span></span>  
  
1.  <span data-ttu-id="f0a86-136">No snap-in de **Certificados** , localize o certificado na pasta **Certificados** / **Pessoal** , clique com o botão direito do mouse em **Certificado**, aponte para **Todas as Tarefas**e clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="f0a86-136">From the **Certificates** snap-in, locate the certificate in the **Certificates** / **Personal** folder, right-click the **Certificate**, point to **All Tasks**, and then click **Export**.</span></span>  
  
2.  <span data-ttu-id="f0a86-137">Complete o **Assistente para Exportação de Certificados**armazenando o arquivo de certificado em um local conveniente.</span><span class="sxs-lookup"><span data-stu-id="f0a86-137">Complete the **Certificate Export Wizard**, storing the certificate file in a convenient location.</span></span>  
  
###  <a name="to-configure-the-server-to-accept-encrypted-connections"></a><a name="ConfigureServerConnections"></a> <span data-ttu-id="f0a86-138">Para configurar o servidor para aceitar conexões criptografadas</span><span class="sxs-lookup"><span data-stu-id="f0a86-138">To configure the server to accept encrypted connections</span></span>  
  
1.  <span data-ttu-id="f0a86-139">No **SQL Server Configuration Manager**, expanda **Configuração de Rede do SQL Server**, clique com o botão direito do mouse em **Protocolos para** _\<server instance>_ e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f0a86-139">In **SQL Server Configuration Manager**, expand **SQL Server Network Configuration**, right-click **Protocols for** _\<server instance>_, and then select**Properties**.</span></span>  
  
2.  <span data-ttu-id="f0a86-140">Na caixa de diálogo **protocolos para** _\<instance name>_ **Propriedades** , na guia **certificado** , selecione o certificado desejado na lista suspensa da caixa **certificado** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0a86-140">In the **Protocols for**_\<instance name>_ **Properties** dialog box, on the **Certificate** tab, select the desired certificate from the drop down for the **Certificate** box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="f0a86-141">Na guia **Sinalizadores** , na caixa **ForceEncryption** , selecione **Sim**e clique em **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f0a86-141">On the **Flags** tab, in the **ForceEncryption** box, select **Yes**, and then click **OK** to close the dialog box.</span></span>  
  
4.  <span data-ttu-id="f0a86-142">Reinicie o serviço [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f0a86-142">Restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
###  <a name="to-configure-the-client-to-request-encrypted-connections"></a><a name="ConfigureClientConnections"></a> <span data-ttu-id="f0a86-143">Para configurar o cliente para solicitar conexões criptografadas</span><span class="sxs-lookup"><span data-stu-id="f0a86-143">To configure the client to request encrypted connections</span></span>  
  
1.  <span data-ttu-id="f0a86-144">Copie o certificado original ou o arquivo de certificado exportado no computador cliente.</span><span class="sxs-lookup"><span data-stu-id="f0a86-144">Copy either the original certificate or the exported certificate file to the client computer.</span></span>  
  
2.  <span data-ttu-id="f0a86-145">No computador cliente, use o snap-in de **Certificados** para instalar o certificado raiz ou o arquivo do certificado exportado.</span><span class="sxs-lookup"><span data-stu-id="f0a86-145">On the client computer, use the **Certificates** snap-in to install either the root certificate or the exported certificate file.</span></span>  
  
3.  <span data-ttu-id="f0a86-146">No painel de console, clique com o botão direito do mouse em **Configuração do SQL Server Native Client**e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f0a86-146">In the console pane, right-click **SQL Server Native Client Configuration**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="f0a86-147">Na página **Sinalizadores** , na caixa **Forçar criptografia de protocolo** , clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f0a86-147">On the **Flags** page, in the **Force protocol encryption** box, click **Yes**.</span></span>  
  
###  <a name="to-encrypt-a-connection-from-sql-server-management-studio"></a><a name="EncryptConnection"></a><span data-ttu-id="f0a86-148">Para criptografar uma conexão de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0a86-148">To encrypt a connection from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="f0a86-149">Na barra de ferramentas do Pesquisador de Objetos, clique em **Conectar**e clique em **Mecanismo de Banco de Dados**.</span><span class="sxs-lookup"><span data-stu-id="f0a86-149">On the Object Explorer toolbar, click **Connect**, and then click **Database Engine**.</span></span>  
  
2.  <span data-ttu-id="f0a86-150">Na caixa de diálogo **Conectar ao Servidor** , complete as informações de conexão e clique em **Opções**.</span><span class="sxs-lookup"><span data-stu-id="f0a86-150">In the **Connect to Server** dialog box, complete the connection information, and then click **Options**.</span></span>  
  
3.  <span data-ttu-id="f0a86-151">Na guia **Propriedades de Conexão** , clique em **Criptografar conexão**.</span><span class="sxs-lookup"><span data-stu-id="f0a86-151">On the **Connection Properties** tab, click **Encrypt connection**.</span></span>  
  
  
