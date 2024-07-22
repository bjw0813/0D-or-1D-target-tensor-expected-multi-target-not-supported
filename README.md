# 0D-or-1D-target-tensor-expected-multi-target-not-supported
nn.CrossEntropyLoss() 혹은 F.cross_entropy 를 사용했을 때 자주 발생한다

그럴떈 스퀴즈를 사용하든 뭘해서 shape을 [n,] 이런 형태로 만들어줘야 한다
nn.CrossEntropyLoss()(pred, target.squeeze(dim=-1))
