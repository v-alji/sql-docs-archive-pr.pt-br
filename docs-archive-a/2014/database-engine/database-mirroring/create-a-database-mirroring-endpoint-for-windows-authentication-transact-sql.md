---
title: Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- database mirroring [SQL Server], endpoint
- endpoints [SQL Server], database mirroring
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: baf1a4b1-6790-4275-b261-490bca33bdb9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5558bc5684f2eb9053c935543db0c05d6225daf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571578"
---
# <a name="create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql"></a><span data-ttu-id="637cf-102">Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="637cf-102">Create a Database Mirroring Endpoint for Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="637cf-103">Este tópico descreve como criar um ponto de extremidade de espelhamento de banco de dados que usa a Autenticação do Windows no [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] usando o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="637cf-103">This topic describes how to create a database mirroring endpoint that uses Windows Authentication in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="637cf-104">Para oferecer suporte ao espelhamento de banco de dados ou ao [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] , cada instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] exige um ponto de extremidade de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="637cf-104">To support database mirroring or [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] requires a database mirroring endpoint.</span></span> <span data-ttu-id="637cf-105">Uma instância do servidor só pode ter em um ponto de extremidade do espelhamento de banco de dados, que tem uma porta única.</span><span class="sxs-lookup"><span data-stu-id="637cf-105">A server instance can have only one database mirroring endpoint, which has a single port.</span></span> <span data-ttu-id="637cf-106">Um ponto de extremidade do espelhamento de banco de dados poderá usar qualquer porta que estiver disponível no sistema local quando o ponto de extremidade for criado.</span><span class="sxs-lookup"><span data-stu-id="637cf-106">A database mirroring endpoint can use any port that is available on the local system when the endpoint is created.</span></span> <span data-ttu-id="637cf-107">Todas as sessões de espelhamento de banco de dados em uma instância do servidor escutam aquela porta e todas as conexões que chegam para o espelhamento de banco de dados usam aquela porta.</span><span class="sxs-lookup"><span data-stu-id="637cf-107">All database mirroring sessions on a server instance listen on that port, and all incoming connections for database mirroring use that port.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="637cf-108">Se um ponto de extremidade do espelhamento de banco de dados existe e já está em uso, é recomendável usar esse ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="637cf-108">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint.</span></span> <span data-ttu-id="637cf-109">O descarte de um ponto de extremidade em uso interrompe sessões existentes.</span><span class="sxs-lookup"><span data-stu-id="637cf-109">Dropping an in-use endpoint disrupts existing sessions.</span></span>  
  
 <span data-ttu-id="637cf-110">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="637cf-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="637cf-111">**Antes de começar:**  [Segurança](#Security)</span><span class="sxs-lookup"><span data-stu-id="637cf-111">**Before you begin:**  [Security](#Security)</span></span>  
  
-   <span data-ttu-id="637cf-112">**Para criar um ponto de extremidade de espelhamento de banco de dados usando:**  [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="637cf-112">**To create a database mirroring endpoint, using:**  [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="637cf-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="637cf-113">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="637cf-114">Segurança</span><span class="sxs-lookup"><span data-stu-id="637cf-114">Security</span></span>  
 <span data-ttu-id="637cf-115">Os métodos de autenticação e de criptografia da instância do servidor são estabelecidos pelo administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="637cf-115">The authentication and encryption methods of the server instance are established by the system administrator.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="637cf-116">O algoritmo RC4 é preterido.</span><span class="sxs-lookup"><span data-stu-id="637cf-116">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="637cf-117">Recomendamos usar AES.</span><span class="sxs-lookup"><span data-stu-id="637cf-117">We recommend that you use AES.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="637cf-118">Permissões</span><span class="sxs-lookup"><span data-stu-id="637cf-118">Permissions</span></span>  
 <span data-ttu-id="637cf-119">Exige a permissão CREATE ENDPOINT ou a associação na função de servidor fixa sysadmin.</span><span class="sxs-lookup"><span data-stu-id="637cf-119">Requires CREATE ENDPOINT permission, or membership in the sysadmin fixed server role.</span></span> <span data-ttu-id="637cf-120">Para obter mais informações, consulte [Permissões GRANT do ponto de extremidade &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="637cf-120">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="637cf-121">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="637cf-121">Using Transact-SQL</span></span>  
  
#### <a name="to-create-a-database-mirroring-endpoint-that-uses-windows-authentication"></a><span data-ttu-id="637cf-122">Para criar um ponto de extremidade do espelhamento de banco de dados que usa a Autenticação do Windows</span><span class="sxs-lookup"><span data-stu-id="637cf-122">To Create a Database Mirroring Endpoint That Uses Windows Authentication</span></span>  
  
1.  <span data-ttu-id="637cf-123">Conecte-se à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] na qual você deseja criar um ponto de extremidade do espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="637cf-123">Connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on which you want to create a database mirroring endpoint.</span></span>  
  
2.  <span data-ttu-id="637cf-124">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="637cf-124">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="637cf-125">Determine se um ponto de extremidade de espelhamento de banco de dados já existe usando a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="637cf-125">Determine if a database mirroring endpoint already exists by using the following statement:</span></span>  
  
    ```sql
    SELECT name, role_desc, state_desc FROM sys.database_mirroring_endpoints;
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="637cf-126">Se um ponto de extremidade do espelhamento de banco de dados já existir para a instância do servidor, use aquele ponto de extremidade para qualquer outra sessão que você estabelecer na instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="637cf-126">If a database mirroring endpoint already exists for the server instance, use that endpoint for any other sessions you establish on the server instance.</span></span>  
  
4.  <span data-ttu-id="637cf-127">Para usar o Transact-SQL para criar um ponto de extremidade para ser usado com a Autenticação do Windows, use uma instrução CREATE ENDPOINT.</span><span class="sxs-lookup"><span data-stu-id="637cf-127">To use Transact-SQL to create an endpoint to use with Windows Authentication, use a CREATE ENDPOINT statement.</span></span> <span data-ttu-id="637cf-128">A instrução leva o seguinte formato geral:</span><span class="sxs-lookup"><span data-stu-id="637cf-128">The statement takes the following general form:</span></span>  
  
     <span data-ttu-id="637cf-129">CREATE ENDPOINT *\<endpointName>*</span><span class="sxs-lookup"><span data-stu-id="637cf-129">CREATE ENDPOINT *\<endpointName>*</span></span>  
  
     <span data-ttu-id="637cf-130">STATE=STARTED</span><span class="sxs-lookup"><span data-stu-id="637cf-130">STATE=STARTED</span></span>  
  
     <span data-ttu-id="637cf-131">AS TCP ( LISTENER_PORT = *\<listenerPortList>* )</span><span class="sxs-lookup"><span data-stu-id="637cf-131">AS TCP ( LISTENER_PORT = *\<listenerPortList>* )</span></span>  
  
     <span data-ttu-id="637cf-132">FOR DATABASE_MIRRORING</span><span class="sxs-lookup"><span data-stu-id="637cf-132">FOR DATABASE_MIRRORING</span></span>  
  
     <span data-ttu-id="637cf-133">(</span><span class="sxs-lookup"><span data-stu-id="637cf-133">(</span></span>  
  
     <span data-ttu-id="637cf-134">[ AUTHENTICATION = **WINDOWS** [ *\<authorizationMethod>* ]</span><span class="sxs-lookup"><span data-stu-id="637cf-134">[ AUTHENTICATION = **WINDOWS** [ *\<authorizationMethod>* ]</span></span>  
  
     <span data-ttu-id="637cf-135">]</span><span class="sxs-lookup"><span data-stu-id="637cf-135">]</span></span>  
  
     <span data-ttu-id="637cf-136">[ [ **,** ] ENCRYPTION = **REQUIRED**</span><span class="sxs-lookup"><span data-stu-id="637cf-136">[ [**,**] ENCRYPTION = **REQUIRED**</span></span>  
  
     <span data-ttu-id="637cf-137">[ ALGORITHM { *\<algorithm>* } ]</span><span class="sxs-lookup"><span data-stu-id="637cf-137">[ ALGORITHM { *\<algorithm>* } ]</span></span>  
  
     <span data-ttu-id="637cf-138">]</span><span class="sxs-lookup"><span data-stu-id="637cf-138">]</span></span>  
  
     <span data-ttu-id="637cf-139">[ **,** ] ROLE = *\<role>*</span><span class="sxs-lookup"><span data-stu-id="637cf-139">[**,**] ROLE = *\<role>*</span></span>  
  
     <span data-ttu-id="637cf-140">)</span><span class="sxs-lookup"><span data-stu-id="637cf-140">)</span></span>  
  
     <span data-ttu-id="637cf-141">onde</span><span class="sxs-lookup"><span data-stu-id="637cf-141">where</span></span>  
  
    -   <span data-ttu-id="637cf-142">*\<endpointName>* é um nome exclusivo para o ponto de extremidade do espelhamento de banco de dados da instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="637cf-142">*\<endpointName>* is a unique name for the database mirroring endpoint of the server instance.</span></span>  
  
    -   <span data-ttu-id="637cf-143">STARTED especifica que o ponto de extremidade deve ser iniciado e começar a escutar conexões.</span><span class="sxs-lookup"><span data-stu-id="637cf-143">STARTED specifies that the endpoint is to be started and to begin listening for connections.</span></span> <span data-ttu-id="637cf-144">Um ponto de extremidade do espelhamento de banco de dados é normalmente criado no estado STARTED.</span><span class="sxs-lookup"><span data-stu-id="637cf-144">A database mirroring endpoint typically is created in the STARTED state.</span></span> <span data-ttu-id="637cf-145">Alternativamente, você pode iniciar uma sessão em um estado STOPPED (o padrão) ou no estado DISABLED.</span><span class="sxs-lookup"><span data-stu-id="637cf-145">Alternatively, you can start a session in a STOPPED state (the default) or DISABLED state.</span></span>  
  
    -   <span data-ttu-id="637cf-146">*\<listenerPortList>* é um número da porta único (*nnnn*) no qual você deseja que o servidor escute mensagens de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="637cf-146">*\<listenerPortList>* is a single port number (*nnnn*) on which you want the server to listen for database mirroring messages.</span></span> <span data-ttu-id="637cf-147">Só o TCP é permitido; se qualquer outro protocolo for especificado causará um erro.</span><span class="sxs-lookup"><span data-stu-id="637cf-147">Only TCP is allowed; specifying any other protocol causes an error.</span></span>  
  
         <span data-ttu-id="637cf-148">Um número de porta só pode ser usado uma vez por um sistema de computador.</span><span class="sxs-lookup"><span data-stu-id="637cf-148">A port number can be used only once per computer system.</span></span> <span data-ttu-id="637cf-149">Um ponto de extremidade do espelhamento de banco de dados poderá usar qualquer porta que estiver disponível no sistema local quando o ponto de extremidade for criado.</span><span class="sxs-lookup"><span data-stu-id="637cf-149">A database mirroring endpoint can use any port that is available on the local system when the endpoint is created.</span></span> <span data-ttu-id="637cf-150">Para identificar as portas que estão sendo usadas atualmente pelos pontos de extremidade de TCP no sistema, use a seguinte instrução Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="637cf-150">To identify the ports currently being used by TCP endpoints on the system, use the following Transact-SQL statement:</span></span>  
  
        ```  
        SELECT name, port FROM sys.tcp_endpoints;  
        ```  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="637cf-151">Cada instância do servidor requer uma e apenas uma porta do ouvinte exclusiva.</span><span class="sxs-lookup"><span data-stu-id="637cf-151">Each server instance requires one and only one unique listener port.</span></span>  
  
    -   <span data-ttu-id="637cf-152">Para a Autenticação do Windows, a opção AUTHENTICATION é opcional, a menos que você deseje que o ponto de extremidade use apenas NTLM ou Kerberos para autenticar conexões.</span><span class="sxs-lookup"><span data-stu-id="637cf-152">For Windows Authentication, the AUTHENTICATION option is optional, unless you want the endpoint to use only NTLM or Kerberos to authenticate connections.</span></span> <span data-ttu-id="637cf-153">*\<authorizationMethod>* especifica o método usado para autenticar conexões como um dos seguintes: NTLM, KERBEROS ou NEGOTIATE.</span><span class="sxs-lookup"><span data-stu-id="637cf-153">*\<authorizationMethod>* specifies the method used to authenticate connections as one of the following: NTLM, KERBEROS, or NEGOTIATE.</span></span> <span data-ttu-id="637cf-154">O padrão, NEGOTIATE, faz o ponto de extremidade usar o protocolo de negociação Windows para escolher NTLM ou Kerberos.</span><span class="sxs-lookup"><span data-stu-id="637cf-154">The default, NEGOTIATE, causes the endpoint to use the Windows negotiation protocol to choose either NTLM or Kerberos.</span></span> <span data-ttu-id="637cf-155">A negociação habilita conexões com ou sem autenticação, dependendo do nível de autenticação do ponto de extremidade oposto.</span><span class="sxs-lookup"><span data-stu-id="637cf-155">Negotiation enables connections with or without authentication, depending on the authentication level of the opposite endpoint.</span></span>  
  
    -   <span data-ttu-id="637cf-156">ENCRYPTION é definido como REQUIRED por padrão.</span><span class="sxs-lookup"><span data-stu-id="637cf-156">ENCRYPTION is set to REQUIRED by default.</span></span> <span data-ttu-id="637cf-157">Isso especifica que todas as conexões para esse ponto de extremidade devem usar criptografia.</span><span class="sxs-lookup"><span data-stu-id="637cf-157">This means that all connections to this endpoint must use encryption.</span></span> <span data-ttu-id="637cf-158">Porém, você pode desabilitar a criptografia ou deixá-la opcional em um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="637cf-158">However, you can disable encryption or make it optional on an endpoint.</span></span> <span data-ttu-id="637cf-159">As alternativas são como segue:</span><span class="sxs-lookup"><span data-stu-id="637cf-159">The alternatives are as follows:</span></span>  
  
        |<span data-ttu-id="637cf-160">Valor</span><span class="sxs-lookup"><span data-stu-id="637cf-160">Value</span></span>|<span data-ttu-id="637cf-161">Definição</span><span class="sxs-lookup"><span data-stu-id="637cf-161">Definition</span></span>|  
        |-----------|----------------|  
        |<span data-ttu-id="637cf-162">DISABLED</span><span class="sxs-lookup"><span data-stu-id="637cf-162">DISABLED</span></span>|<span data-ttu-id="637cf-163">Especifica que os dados enviados em uma conexão não estão criptografados.</span><span class="sxs-lookup"><span data-stu-id="637cf-163">Specifies that data sent over a connection is not encrypted.</span></span>|  
        |<span data-ttu-id="637cf-164">SUPPORTED</span><span class="sxs-lookup"><span data-stu-id="637cf-164">SUPPORTED</span></span>|<span data-ttu-id="637cf-165">Especifica que os dados só serão criptografados se o ponto de extremidade oposto especificar SUPPORTED ou REQUIRED.</span><span class="sxs-lookup"><span data-stu-id="637cf-165">Specifies that the data is encrypted only if the opposite endpoint specifies either SUPPORTED or REQUIRED.</span></span>|  
        |<span data-ttu-id="637cf-166">REQUIRED</span><span class="sxs-lookup"><span data-stu-id="637cf-166">REQUIRED</span></span>|<span data-ttu-id="637cf-167">Especifica que os dados enviados em uma conexão devem ser criptografados.</span><span class="sxs-lookup"><span data-stu-id="637cf-167">Specifies that data sent over a connection must be encrypted.</span></span>|  
  
         <span data-ttu-id="637cf-168">Se um ponto de extremidade requisitar criptografia, o outro ponto de extremidade deve ter ENCRYPTION definido como SUPPORTED ou REQUIRED.</span><span class="sxs-lookup"><span data-stu-id="637cf-168">If an endpoint requires encryption, the other endpoint must have ENCRYPTION set to either SUPPORTED or REQUIRED.</span></span>  
  
    -   <span data-ttu-id="637cf-169">*\<algorithm>* fornece a opção de especificar os padrões de criptografia para o ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="637cf-169">*\<algorithm>* provides the option of specifying the encryption standards for the endpoint.</span></span> <span data-ttu-id="637cf-170">O valor de *\<algorithm>* pode ser um dos seguintes algoritmos ou combinações de algoritmos: RC4, AES, AES RC4 ou RC4 AES.</span><span class="sxs-lookup"><span data-stu-id="637cf-170">The value of *\<algorithm>* can be one following algorithms or combinations of algorithms: RC4, AES, AES RC4, or RC4 AES.</span></span>  
  
         <span data-ttu-id="637cf-171">AES RC4 especifica que esse ponto de extremidade negociará um algoritmo de criptografia, dando preferência ao algoritmo AES.</span><span class="sxs-lookup"><span data-stu-id="637cf-171">AES RC4 specifies that this endpoint will negotiate for the encryption algorithm, giving preference to the AES algorithm.</span></span> <span data-ttu-id="637cf-172">RC4 AES especifica que esse ponto de extremidade negociará um algoritmo de criptografia, dando preferência ao algoritmo RC4.</span><span class="sxs-lookup"><span data-stu-id="637cf-172">RC4 AES specifies that this endpoint will negotiate for the encryption algorithm, giving preference to the RC4 algorithm.</span></span> <span data-ttu-id="637cf-173">Se ambos os ponto de extremidade especificarem ambos os algoritmos, mas em ordens diferentes, vence o ponto de extremidade que aceita a conexão.</span><span class="sxs-lookup"><span data-stu-id="637cf-173">If both endpoints specify both algorithms but in different orders, the endpoint accepting the connection wins.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="637cf-174">O algoritmo RC4 é preterido.</span><span class="sxs-lookup"><span data-stu-id="637cf-174">The RC4 algorithm is deprecated.</span></span> [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="637cf-175">Recomendamos usar AES.</span><span class="sxs-lookup"><span data-stu-id="637cf-175">We recommend that you use AES.</span></span>  
  
    -   <span data-ttu-id="637cf-176">*\<role>* define a função ou as funções que o servidor pode executar.</span><span class="sxs-lookup"><span data-stu-id="637cf-176">*\<role>* defines the role or roles that the server can perform.</span></span> <span data-ttu-id="637cf-177">Especificar ROLE é necessário.</span><span class="sxs-lookup"><span data-stu-id="637cf-177">Specifying ROLE is required.</span></span> <span data-ttu-id="637cf-178">Entretanto, a função do ponto de extremidade é relevante apenas para o espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="637cf-178">However, the role of the endpoint is relevant only for database mirroring.</span></span> <span data-ttu-id="637cf-179">Para [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], a função do ponto de extremidade é ignorada.</span><span class="sxs-lookup"><span data-stu-id="637cf-179">For [!INCLUDE[ssHADR](../../includes/sshadr-md.md)], the role of the endpoint is ignored.</span></span>  
  
         <span data-ttu-id="637cf-180">Para permitir que uma instância do servidor sirva como uma função em uma sessão de espelhamento de banco de dados e uma função diferente em outra sessão, especifique ROLE=ALL.</span><span class="sxs-lookup"><span data-stu-id="637cf-180">To allow a server instance to serve as one role for one database mirroring session and different role for another session, specify ROLE=ALL.</span></span> <span data-ttu-id="637cf-181">Para restringir uma instância do servidor como sendo um parceiro ou uma testemunha, especifique ROLE=PARTNER ou ROLE=WITNESS, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="637cf-181">To restrict a server instance to being either a partner or a witness, specify ROLE=PARTNER or ROLE=WITNESS, respectively.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="637cf-182">Para obter mais informações sobre opções de espelhamento de banco de dados para edições diferentes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consulte [recursos com suporte nas edições do SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="637cf-182">For more information about Database Mirroring options for different editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
     <span data-ttu-id="637cf-183">Para obter uma descrição completa da sintaxe CREATE ENDPOINT, veja [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="637cf-183">For a complete description of the CREATE ENDPOINT syntax, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="637cf-184">Para alterar um ponto de extremidade existente, use [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="637cf-184">To change an existing endpoint, use [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
###  <a name="example-creating-endpoints-to-support-for-database-mirroring-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="637cf-185">Exemplo: criar pontos de extremidade compatíveis com espelhamento de banco de dados (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="637cf-185">Example: Creating Endpoints to Support for Database Mirroring (Transact-SQL)</span></span>  
 <span data-ttu-id="637cf-186">O seguinte exemplo cria pontos de extremidade do espelhamento de banco de dados para as instâncias de servidor padrão em três sistemas de computador separados:</span><span class="sxs-lookup"><span data-stu-id="637cf-186">The following example creates database mirroring endpoints for the default server instances on three separate computer systems:</span></span>  
  
|<span data-ttu-id="637cf-187">Função da instância de servidor</span><span class="sxs-lookup"><span data-stu-id="637cf-187">Role of server instance</span></span>|<span data-ttu-id="637cf-188">Nome do computador host</span><span class="sxs-lookup"><span data-stu-id="637cf-188">Name of host computer</span></span>|  
|-----------------------------|---------------------------|  
|<span data-ttu-id="637cf-189">Parceiro (inicialmente na função principal)</span><span class="sxs-lookup"><span data-stu-id="637cf-189">Partner (initially in the principal role)</span></span>|`SQLHOST01\.`|  
|<span data-ttu-id="637cf-190">Parceiro (inicialmente na função espelho)</span><span class="sxs-lookup"><span data-stu-id="637cf-190">Partner (initially in the mirror role)</span></span>|`SQLHOST02\.`|  
|<span data-ttu-id="637cf-191">Witness (testemunha)</span><span class="sxs-lookup"><span data-stu-id="637cf-191">Witness</span></span>|`SQLHOST03\.`|  
  
 <span data-ttu-id="637cf-192">Neste exemplo, todos os três pontos de extremidade usam o número da porta 7022, entretanto qualquer número de porta disponível funcionaria.</span><span class="sxs-lookup"><span data-stu-id="637cf-192">In this example, all three endpoints use port number 7022, though any available port number would work.</span></span> <span data-ttu-id="637cf-193">A opção AUTHENTICATION é desnecessária, porque os pontos de extremidade usam o tipo padrão, Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="637cf-193">The AUTHENTICATION option is unnecessary, because the endpoints use the default type, Windows Authentication.</span></span> <span data-ttu-id="637cf-194">A opção ENCRYPTION também é desnecessária, porque todos os pontos de extremidade são feitos para negociar o método de autenticação de uma conexão, que é o comportamento padrão para a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="637cf-194">The ENCRYPTION option is also unnecessary, because the endpoints are all intended to negotiate the authentication method for a connection, which is the default behavior for Windows Authentication.</span></span> <span data-ttu-id="637cf-195">Também, todos os pontos de extremidade requerem a criptografia, que é o comportamento padrão.</span><span class="sxs-lookup"><span data-stu-id="637cf-195">Also, all of the endpoints require the encryption, which is the default behavior.</span></span>  
  
 <span data-ttu-id="637cf-196">Toda instância do servidor está limitada para servir como parceiro ou testemunha, e o ponto de extremidade de cada servidor especifica expressamente qual a função (ROLE=PARTNER ou ROLE=WITNESS).</span><span class="sxs-lookup"><span data-stu-id="637cf-196">Each server instance is limited to serving as either a partner or a witness, and the endpoint of each server expressly specifies which role (ROLE=PARTNER or ROLE=WITNESS).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="637cf-197">Cada instância do servidor só pode ter um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="637cf-197">Each server instance can have only one endpoint.</span></span> <span data-ttu-id="637cf-198">Então, se você quiser que uma instância do servidor seja parceiro em algumas sessões e testemunha em outras, especifique ROLE=ALL.</span><span class="sxs-lookup"><span data-stu-id="637cf-198">Therefore, if you want a server instance to be a partner in some sessions and the witness in others, specify ROLE=ALL.</span></span>  
  
```sql
--Endpoint for initial principal server instance, which  
--is the only server instance running on SQLHOST01.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=PARTNER);  
GO  
--Endpoint for initial mirror server instance, which  
--is the only server instance running on SQLHOST02.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=PARTNER);  
GO  
--Endpoint for witness server instance, which  
--is the only server instance running on SQLHOST03.  
CREATE ENDPOINT endpoint_mirroring  
    STATE = STARTED  
    AS TCP ( LISTENER_PORT = 7022 )  
    FOR DATABASE_MIRRORING (ROLE=WITNESS);  
GO  
```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="637cf-199">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="637cf-199">Related Tasks</span></span>  

### <a name="to-configure-a-database-mirroring-endpoint"></a><span data-ttu-id="637cf-200">Para configurar um ponto de extremidade de espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="637cf-200">To Configure a Database Mirroring Endpoint</span></span>
  
-   [<span data-ttu-id="637cf-201">Criar um ponto de extremidade de espelhamento de banco de dados para Grupos de Disponibilidade AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="637cf-201">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](../availability-groups/windows/database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="637cf-202">Usar certificados para um ponto de extremidade de espelhamento de banco de dados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="637cf-202">Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;</span></span>](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md)  
  
    -   [<span data-ttu-id="637cf-203">Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de saída &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="637cf-203">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
    -   [<span data-ttu-id="637cf-204">Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de entrada &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="637cf-204">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="637cf-205">Especificar um endereço de rede do servidor &#40;Espelhamento de banco de dados&#41;</span><span class="sxs-lookup"><span data-stu-id="637cf-205">Specify a Server Network Address &#40;Database Mirroring&#41;</span></span>](specify-a-server-network-address-database-mirroring.md)  
  
-   [<span data-ttu-id="637cf-206">Especificar a URL do ponto de extremidade ao adicionar ou modificar uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="637cf-206">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](../availability-groups/windows/specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
 <span data-ttu-id="637cf-207">**Para exibir informações sobre o ponto de extremidade de espelhamento de banco de dados**</span><span class="sxs-lookup"><span data-stu-id="637cf-207">**To View Information About the Database Mirroring Endpoint**</span></span>  
  
-   [<span data-ttu-id="637cf-208">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="637cf-208">sys.database_mirroring_endpoints &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="637cf-209">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="637cf-209">See Also</span></span>  
 <span data-ttu-id="637cf-210">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="637cf-210">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="637cf-211">[Escolher um algoritmo de criptografia](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="637cf-211">[Choose an Encryption Algorithm](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span></span>  
 <span data-ttu-id="637cf-212">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="637cf-212">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="637cf-213">[Especificar um endereço de rede do servidor &#40;espelhamento de banco de dados&#41;](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="637cf-213">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="637cf-214">[Exemplo: configurar o espelhamento de banco de dados usando a Autenticação do Windows &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="637cf-214">[Example: Setting Up Database Mirroring Using Windows Authentication &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-windows-authentication-transact-sql.md) </span></span>  
 [<span data-ttu-id="637cf-215">O ponto de extremidade de espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="637cf-215">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
