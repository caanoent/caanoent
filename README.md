- 👋 Hi, I’m @caanoent
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
caanoent/caanoent is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

CWallet::ResendWalletTransactions in wallet.cpp.
 See: 
pnodeTrickle = vNodesCopy[GetRand(vNodesCopy.size())];
and 
SendMessages(pnode, pnode == pnodeTrickle);
in ThreadMessageHandler2() in net.cpp.
 See:
//
// Message: addr
//
if (fSendTrickle)
{ 
in SendMessages() in main.cpp.
 See: 
bool fTrickleWait = ((hashRand & 3) != 0);
in SendMessages() in main.cpp.
 See:
// trickle out tx inv to protect privacy
if (inv.type == MSG_TX && !fSendTrickle)
{ 
in SendMessages() in main.cpp.
 See:
// always trickle our own transactions
if (!fTrickleWait)
{ 
CWalletTx wtx;
if (GetTransaction(inv.hash, wtx))
if (wtx.fFromMe)
fTrickleWait = true;
}
