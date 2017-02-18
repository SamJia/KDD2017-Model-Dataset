#CTCD

##Compile

Get into the 'CTCD' directory and use 'make' command to compile.
Two executable file are generated, ctcd and ctcd_ber, which represent the CTCD and CTCD-Ber respectively.
Has been tested on Ubuntu with g++ 6.2.0, and on Windows with MinGW-w64 6.2.0.

##Usage
###Parameters
    -i: Input data's folder path(default: .)
    -o: Output Graph data prefix(default: .)
    -tm: Number of threads for parallelization(default: number of cores)
    -cc: The number of communities to detect(default: 10)
    -tc: The number of topics in one community to detect(default: 10)
    -ic: Number of update iterations(default: 200)
    -sic: How many iterations for once save(default: 50)
    -alpha: Alpha(default: 0.1)
    -beta: Beta(default: 0.1)
    -epsilon: Epsilon(default: 0.1)
    -rho: Rho(default: 0.1)
    -sigma: Sigma(default: 0.1)
    -lambda0: Lambda0(default: 0.1)
    -lambdaweight: Lambda's tunable weight(default: 1)

###Examples
    ./ctcd -i input_dir -o output_predix -lambdaweight 16
    ./ctcd_ber -i input_dir -o output_predix -lambdaweight 16

#Dataset

##Link

Academia: http://acemap.sjtu.edu.cn/app/KDD2017-146/Datasets/Academia.zip

Weibo: http://acemap.sjtu.edu.cn/app/KDD2017-146/Datasets/Weibo.zip

##Format

docs.txt: Each line means a post. user(tab)time(tab)words. Words are space seperated

links.txt: each line means one link. user1(tab)user2(tab)time_pairs. Time_pairs are tab seperated and each time_pair is recorded as out_time(space)in_time.

For Weibo, because the text is in Chinese which is not convenient to use in C++, we map each word as a numerical id, and the mapping is save in 'word_dict.json' as standard json format.
