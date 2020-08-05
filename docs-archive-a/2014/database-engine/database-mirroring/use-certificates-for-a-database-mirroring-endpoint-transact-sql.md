---
title: Usar certificados para um ponto de extremidade de espelhamento de banco de dados (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- certificates [SQL Server], database mirroring
- authentication [SQL Server], database mirroring
- database mirroring [SQL Server], security
ms.assetid: f7c23cc2-48dc-4b78-b441-89ca29a0bd9e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c159e66e798524c41bf6e653283c299cc8393be5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572682"
---
# <a name="use-certificates-for-a-database-mirroring-endpoint-transact-sql"></a><span data-ttu-id="0460d-102">Usar certificados para um ponto de extremidade de espelhamento de banco de dados (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0460d-102">Use Certificates for a Database Mirroring Endpoint (Transact-SQL)</span></span>
  <span data-ttu-id="0460d-103">Para habilitar a autenticação de certificado para espelhamento de banco de dados em uma determinada instância do servidor, o administrador do sistema deve configurar cada instância do servidor para usar certificados nas conexões de saída e de entrada.</span><span class="sxs-lookup"><span data-stu-id="0460d-103">To enable certificate authentication for database mirroring on a given server instance, the system administrator must configure each server instance to use certificates on both outbound and inbound connections.</span></span> <span data-ttu-id="0460d-104">As conexões de saída devem ser configuradas primeiro.</span><span class="sxs-lookup"><span data-stu-id="0460d-104">Outbound connections must be configured first.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0460d-105">Todas as conexões de espelhamento em uma instância do servidor usam um único ponto de extremidade de espelhamento do banco de dados e você deve especificar o método de autenticação da instância do servidor quando criar o ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="0460d-105">All mirroring connections on a server instance use a single database mirroring endpoint, and you must specify the authentication method of the server instance when you create the endpoint.</span></span> <span data-ttu-id="0460d-106">Portanto, você pode usar somente um formulário de autenticação por instância do servidor para espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0460d-106">Therefore, you can use only one form of authentication per server instance for database mirroring.</span></span>  
  
## <a name="configuring-outbound-connections"></a><span data-ttu-id="0460d-107">Configurando conexões de saída</span><span class="sxs-lookup"><span data-stu-id="0460d-107">Configuring Outbound Connections</span></span>  
 <span data-ttu-id="0460d-108">Siga essas etapas em cada instância do servidor que você está configurando para espelhamento de banco de dados:</span><span class="sxs-lookup"><span data-stu-id="0460d-108">Follow these steps on each server instance that you are configuring for database mirroring:</span></span>  
  
1.  <span data-ttu-id="0460d-109">No banco de dados **mestre** , crie uma chave mestra de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0460d-109">In the **master** database, create a database master key.</span></span>  
  
2.  <span data-ttu-id="0460d-110">No banco de dados **mestre** , crie um certificado criptografado na instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="0460d-110">In the **master** database, create an encrypted certificate on the server instance.</span></span>  
  
3.  <span data-ttu-id="0460d-111">Crie um ponto de extremidade para a instância do servidor que usa seu certificado.</span><span class="sxs-lookup"><span data-stu-id="0460d-111">Create an endpoint for the server instance using its certificate.</span></span>  
  
4.  <span data-ttu-id="0460d-112">Faça o backup do certificado em um arquivo e o copie-o com segurança para outro sistema ou sistemas.</span><span class="sxs-lookup"><span data-stu-id="0460d-112">Back up the certificate to a file and securely copy it to the other system or systems.</span></span>  
  
 <span data-ttu-id="0460d-113">Você deve completar essas etapas para cada parceiro e para a testemunha, se houver.</span><span class="sxs-lookup"><span data-stu-id="0460d-113">You must complete these steps for each partner and the witness, if there is one.</span></span>  
  
 <span data-ttu-id="0460d-114">Para obter mais informações, consulte [Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de saída &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="0460d-114">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
## <a name="configuring-inbound-connections"></a><span data-ttu-id="0460d-115">Configurando conexões de saída</span><span class="sxs-lookup"><span data-stu-id="0460d-115">Configuring Inbound Connections</span></span>  
 <span data-ttu-id="0460d-116">A seguir, siga estas etapas para cada parceiro que você está configurando para espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0460d-116">Next, follow these steps for each partner that you are configuring for database mirroring.</span></span> <span data-ttu-id="0460d-117">No banco de dados **mestre** :</span><span class="sxs-lookup"><span data-stu-id="0460d-117">In the **master** database:</span></span>  
  
1.  <span data-ttu-id="0460d-118">Crie um logon para o outro sistema.</span><span class="sxs-lookup"><span data-stu-id="0460d-118">Create a login for the other system.</span></span>  
  
2.  <span data-ttu-id="0460d-119">Crie um usuário para aquele logon.</span><span class="sxs-lookup"><span data-stu-id="0460d-119">Create a user for that login.</span></span>  
  
3.  <span data-ttu-id="0460d-120">Obtenha o certificado para o ponto de extremidade de espelhamento da outra instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="0460d-120">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
4.  <span data-ttu-id="0460d-121">Associe o certificado ao usuário criado na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="0460d-121">Associate the certificate with the user created in step 2.</span></span>  
  
5.  <span data-ttu-id="0460d-122">Conceda permissão CONNECT no logon para aquele ponto de extremidade de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="0460d-122">Grant CONNECT permission on the login for that mirroring endpoint.</span></span>  
  
 <span data-ttu-id="0460d-123">Se houver uma testemunha, deve-se configurar também conexões de entrada para ela.</span><span class="sxs-lookup"><span data-stu-id="0460d-123">If there is a witness, you must also set up inbound connections for it.</span></span> <span data-ttu-id="0460d-124">Isso requer configuração de logons, usuários e certificados para a testemunha nos dois parceiros, e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="0460d-124">This requires setting up logins, users, and certificates for the witness on both of the partners, and vice versa.</span></span>  
  
 <span data-ttu-id="0460d-125">Para obter mais informações, consulte [Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de entrada &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="0460d-125">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="0460d-126">Segurança</span><span class="sxs-lookup"><span data-stu-id="0460d-126">Security</span></span>  
 <span data-ttu-id="0460d-127">A menos que você possa garantir que sua rede está segura, recomendamos o uso de criptografia para conexões de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0460d-127">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span> <span data-ttu-id="0460d-128">Para obter mais informações, consulte [O ponto de extremidade de espelhamento de banco de dados &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="0460d-128">For more information, see [The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md).</span></span>  
  
 <span data-ttu-id="0460d-129">Ao copiar um certificado para outro sistema, use um método de cópia seguro.</span><span class="sxs-lookup"><span data-stu-id="0460d-129">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="0460d-130">Seja extremamente cauteloso para manter todos os seus certificados em segurança.</span><span class="sxs-lookup"><span data-stu-id="0460d-130">Be extremely careful to keep all of your certificates secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0460d-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0460d-131">See Also</span></span>  
 <span data-ttu-id="0460d-132">[Criar uma chave mestra de banco de dados](../../relational-databases/security/encryption/create-a-database-master-key.md) </span><span class="sxs-lookup"><span data-stu-id="0460d-132">[Create a Database Master Key](../../relational-databases/security/encryption/create-a-database-master-key.md) </span></span>  
 <span data-ttu-id="0460d-133">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0460d-133">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span></span>  
 <span data-ttu-id="0460d-134">[Segurança de transporte para espelhamento de banco de dados e Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="0460d-134">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="0460d-135">[Central de segurança do Mecanismo de Banco de Dados do SQL Server e Banco de Dados SQL do Azure](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md) </span><span class="sxs-lookup"><span data-stu-id="0460d-135">[Security Center for SQL Server Database Engine and Azure SQL Database](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md) </span></span>  
 [<span data-ttu-id="0460d-136">O ponto de extremidade de espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="0460d-136">The Database Mirroring Endpoint &#40;SQL Server&#41;</span></span>](the-database-mirroring-endpoint-sql-server.md)  
  
  
