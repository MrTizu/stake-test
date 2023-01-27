<template>
  <div class="dashboard">
    <div class="boxe">
      <div class="box0">
        <div class="statsD">
          <div class="stats1">
            <div class="itemsD">Block Height</div>
            <div class="valueD">{{ (+height).toLocaleString() }}</div>
          </div>

          <div class="stats1">
            <div class="itemsD">Avg. Block Time</div>
            <div class="valueD">1.2 seconds</div>
          </div>
          <div class="stats1">
            <div class="itemsD">Staking APY</div>
            <div class="valueD">{{ (+stakingAPY).toFixed(2) + " %" }}</div>
          </div>

          <div class="stats1">
            <div class="itemsD">Locked Coins</div>
            <div class="valueD">{{ (+totalStake).toLocaleString() }}</div>
          </div>

          <div class="stats1">
            <div class="itemsD">Pct. Of Total</div>
            <div class="valueD">{{ (+percentLock).toFixed(2) }} %</div>
          </div>

          <div class="stats1">
            <div class="itemsD">Circ. Supply</div>
            <div class="valueD">{{ (+circcc).toLocaleString() }}</div>
          </div>

          <div class="stats1">
            <div class="itemsD">Total Supply</div>
            <div class="valueD">{{ (+totalSupp).toLocaleString() }}</div>
          </div>

          <div class="stats1">
            <div class="itemsD">Pct. of Max</div>
            <div class="valueD">{{ (+percentMax).toFixed(2) }} %</div>
          </div>

          <div class="stats1">
            <div class="itemsD">Max Supply</div>
            <div class="valueD">50,000,000</div>
          </div>

          <div class="stats1">
            <div class="itemsD">NEAT coin Price</div>
            <div class="valueD">$ {{ (+priceUSD).toFixed(4) }}</div>
          </div>

          <div class="stats1">
            <div class="itemsD">24h Change</div>
            <div class="valueD">{{ (+price24h).toFixed(2) }} %</div>
          </div>

          <div class="stats1">
            <div class="itemsD">Market CAP</div>
            <div class="valueD">$ {{ (+marketCap).toLocaleString() }}</div>
          </div>
        </div>
      </div>
      <div class="boxes">
        <div class="box1">

          <div class="pools">
            <div class="vAddy1" id="pool2">
              <span style="color: #496785">1.</span> {{ "ROMANIA POOL" }}
              <span style="color: #496785">Pool Fee:</span>
              <span
                style="
                  font-family: Helvetica;
                  font-weight: normal;
                  font-size: 14px;
                "
                >{{ vComm }}</span
              >
              <span style="color: #496785">Staking Power:</span>
              <span
                style="
                  font-family: Helvetica;
                  font-weight: normal;
                  font-size: 14px;
                "
                >{{ (+v44power).toLocaleString() }}</span
              >
              <button
                class="rippleSelect"
                v-show="staking == 0 && rewards == 0 && sPool === null"
                @click="select2"
              >
                SELECT
              </button>
              <button
                class="rippleSelect"
                v-show="staking == 0 && rewards == 0 && sPool !== null"
                @click="neatioStake"
              >
                STAKE
              </button>
              <span
                v-show="staking != 0"
                style="
                  color: #496785;
                  font-size: 14px;
                  font-weight: normal;
                  font-family: Pirulen, Helvetica;
                "
              >
                NEAT</span
              >
            </div>
            <div class="sep"></div>
          </div>


          <div class="pools">
            <div class="vAddy11" id="pool0">
              <span style="color: #496785">2.</span> {{ "DAMUN 8 POOL" }}
              <span style="color: #496785">Pool Fee:</span>
              <span
                style="
                  font-family: Helvetica;
                  font-weight: normal;
                  font-size: 14px;
                "
                >{{ vComm }}</span
              >
              <span style="color: #496785">Staking Power:</span>
              <span
                style="
                  font-family: Helvetica;
                  font-weight: normal;
                  font-size: 14px;
                "
                >{{ (+v22power).toLocaleString() }}</span
              >
              <button
                class="rippleSelect"
                v-show="staking == 0 && rewards == 0 && sPool === null"
                @click="select0"
              >
                SELECT
              </button>
              <button
                class="rippleSelect"
                v-show="staking == 0 && rewards == 0 && sPool !== null"
                @click="neatioStake"
              >
                STAKE
              </button>
              <span
                v-show="staking != 0"
                style="
                  color: #496785;
                  font-size: 14px;
                  font-weight: normal;
                  font-family: Pirulen, Helvetica;
                "
              >
                NEAT</span
              >
            </div>

            <div class="sep"></div>
          </div>



          <div class="pools">
            <div class="vAddy11" id="pool1">
              <span style="color: #496785">3.</span> {{ "NEATIO - ASIA -" }}
              <span style="color: #496785">Pool Fee:</span>
              <span
                style="
                  font-family: Helvetica;
                  font-weight: normal;
                  font-size: 14px;
                "
                >{{ vComm }}</span
              >
              <span style="color: #496785">Staking Power:</span>
              <span
                style="
                  font-family: Helvetica;
                  font-weight: normal;
                  font-size: 14px;
                "
                >{{ (+v33power).toLocaleString() }}</span
              >
              <button
                class="rippleSelect"
                v-show="staking == 0 && rewards == 0 && sPool === null"
                @click="select1"
              >
                SELECT
              </button>
              <button
                class="rippleSelect"
                v-show="staking == 0 && rewards == 0 && sPool !== null"
                @click="neatioStake"
              >
                STAKE
              </button>
              <span
                v-show="staking != 0"
                style="
                  color: #496785;
                  font-size: 14px;
                  font-weight: normal;
                  font-family: Pirulen, Helvetica;
                "
              >
                NEAT</span
              >
            </div>

            <div class="sep"></div>
          </div>



          <div class="pools">
            <div class="vAddy1" id="pool3">
              <span style="color: #496785">4.</span> {{ "SILVIU25 POOL" }}
              <span style="color: #496785">Pool Fee:</span>
              <span
                style="
                  font-family: Helvetica;
                  font-weight: normal;
                  font-size: 14px;
                "
                >{{ vComm }}</span
              >
              <span style="color: #496785">Staking Power:</span>
              <span
                style="
                  font-family: Helvetica;
                  font-weight: normal;
                  font-size: 14px;
                "
                >{{ (+v55power).toLocaleString() }}</span
              >
              <button
                class="rippleSelect"
                v-show="staking == 0 && rewards == 0 && sPool === null"
                @click="select3"
              >
                SELECT
              </button>
              <button
                class="rippleSelect"
                v-show="staking == 0 && rewards == 0 && sPool !== null"
                @click="neatioStake"
              >
                STAKE
              </button>
              <span
                v-show="staking != 0"
                style="
                  color: #496785;
                  font-size: 14px;
                  font-weight: normal;
                  font-family: Pirulen, Helvetica;
                "
              >
                NEAT</span
              >
            </div>

            <div class="sep"></div>
          </div>

          <div class="pools">
            <div class="vAddy2" id="pool4">
              <span style="color: #496785">5.</span> {{ "KINGNODE - EU" }}
              <span style="color: #496785">Pool Fee:</span>
              <span
                style="
                  font-family: Helvetica;
                  font-weight: normal;
                  font-size: 14px;
                "
                >{{ vComm }}</span
              >
              <span style="color: #496785">Staking Power:</span>
              <span
                style="
                  font-family: Helvetica;
                  font-weight: normal;
                  font-size: 14px;
                "
                >{{ (+v66power).toLocaleString() }}</span
              >
              <button
                class="rippleSelect"
                v-show="staking == 0 && rewards == 0 && sPool === null"
                @click="select4"
              >
                SELECT
              </button>
              <button
                class="rippleSelect"
                v-show="staking == 0 && rewards == 0 && sPool !== null"
                @click="neatioStake"
              >
                STAKE
              </button>
              <span
                v-show="staking != 0"
                style="
                  color: #496785;
                  font-size: 14px;
                  font-weight: normal;
                  font-family: Pirulen, Helvetica;
                "
              >
                NEAT</span
              >
            </div>
          </div>
          <!-- 4 END -->
        </div>
        <div class="box2">
          <div class="lockked" v-show="address === ''">
            <img src="../../assets/lock.png" alt="Lock" class="lockimg" />
          </div>

          <div class="locked" v-show="address === ''">
            Please unlock your wallet!
          </div>
          <div class="neatStaking">
            <div class="balance-details" v-show="address != ''">
              <div class="wallet-balance" v-show="address !== ''">
                <div class="addry-w">{{ addry }}</div>
                <div class="walBalT">
                  {{ (+balance).toFixed(6)
                  }}<span
                    style="
                      color: #496785;
                      font-size: 22px;
                      font-weight: normal;
                      font-family: Pirulen, Helvetica;
                    "
                  >
                    NEAT</span
                  >
                </div>
              </div>

              <div class="sep"></div>

              <div class="boxess">
                <div class="wallet-balance-available2">
                  <div class="wl">
                    <img
                      src="../../assets/claim.png"
                      alt="stake"
                      class="walimg"
                    />
                  </div>

                  <div>
                    <span
                      style="
                        color: #496785;
                        font-weight: lighter;
                        font-size: 11px;
                        font-family: Pirulen, Helvetica;
                      "
                      >Coins In Stake</span
                    >
                  </div>
                  <span style="color: #496785; font-family: Helvetica">{{
                    (+staking).toFixed(6)
                  }}</span>
                </div>

                <div class="wallet-balance-available2">
                  <div class="wl">
                    <div class="spinr">
                      <orbit-spinner
                        :animation-duration="1200"
                        :size="55"
                        color="#00ffff"
                        alt="stake"
                      />
                    </div>
                  </div>
                  <span
                    style="
                      color: #496785;

                      font-weight: lighter;
                      font-size: 11px;
                      font-family: Pirulen, Helvetica;
                    "
                    >Unclaimed Rewards</span
                  >
                  <span style="color: #496785; font-family: Helvetica">{{
                    (+rewards).toFixed(18)
                  }}</span>
                </div>
              </div>

              <div
                class="noSel"
                v-show="selectedPool == null && staking == 0 && rewards == 0"
              >
                select a pool if you wish to stake your coins
              </div>

              <div class="deleg" v-show="selectedPool != null">
                Selected pool
                <span
                  style="
                    font-size: 14px;
                    color: #00ffff;
                    font-weight: normal;
                    font-family: Pirulen, Helvetica;
                  "
                  >{{ selectedPool }}</span
                >
              </div>
              <div class="deleg" v-show="staking != 0 && rewards != 0">
                Staking on:
                <span
                  style="
                    font-size: 14px;
                    color: #00ffff;
                    font-weight: normal;
                    font-family: Pirulen, Helvetica;
                  "
                  >{{ stakedTo }}</span
                >
              </div>
              <div class="deleg" v-show="rewards > 0">
                Rewards on:
                <span
                  style="
                    font-size: 14px;
                    color: #00ffff;
                    font-weight: normal;
                    font-family: Pirulen, Helvetica;
                  "
                  >{{ stakedTo }}</span
                >
              </div>
              <div
                class="btnss"
                v-show="
                  (staking != null && selectedPool == 'DAMUN 8 POOL') ||
                  (staking != null && stakedTo == 'DAMUN 8 POOL') ||
                  stakedTo == 'DAMUN 8 POOL'
                "
              >
                <div class="buttns">
                  <button class="rippleStake" @click="neatStake0">stake</button>
                  <button class="rippleClaims" @click="claimRwd0">claim</button>
                  <button class="rippleClaims" @click="unStake0">
                    unstake
                  </button>
                </div>
              </div>

              <div class="btnss" v-show="(staking != null && selectedPool == 'NEATIO - ASIA -') ||
              (staking != null && stakedTo == 'NEATIO - ASIA -') ||
              stakedTo == 'NEATIO - ASIA -'">
                <div class="buttns">
                  <button class="rippleStake" @click="neatStake1">stake</button>
                  <button class="rippleClaims" @click="claimRwd1">claim</button>
                  <button class="rippleClaims" @click="unStake1">
                    unstake
                  </button>
                </div>
              </div>

              <div
                class="btnss"
                v-show="
                  (staking != null && selectedPool == 'ROMANIA POOL') ||
                  (staking != null && stakedTo == 'ROMANIA POOL') ||
                  stakedTo == 'ROMANIA POOL'
                "
              >
                <div class="buttns">
                  <button class="rippleStake" @click="neatStake2">stake</button>
                  <button class="rippleClaims" @click="claimRwd2">claim</button>
                  <button class="rippleClaims" @click="unStake2">
                    unstake
                  </button>
                </div>
              </div>

              <div
                class="btnss"
                v-show="
                  (staking != null && selectedPool == 'SILVIU25 POOL') ||
                  (staking != null && stakedTo == 'SILVIU25 POOL') ||
                  stakedTo == 'SILVIU25 POOL'
                "
              >
                <div class="buttns">
                  <button class="rippleStake" @click="neatStake3">stake</button>
                  <button class="rippleClaims" @click="claimRwd3">claim</button>
                  <button class="rippleClaims" @click="unStake3">
                    unstake
                  </button>
                </div>
              </div>

              <div
                class="btnss"
                v-show="
                  (staking != null && selectedPool == 'KINGNODE - EU') ||
                  (staking != null && stakedTo == 'KINGNODE - EU') ||
                  stakedTo == 'KINGNODE - EU'
                "
              >
                <div class="buttns">
                  <button class="rippleStake" @click="neatStake4">stake</button>
                  <button class="rippleClaims" @click="claimRwd4">claim</button>
                  <button class="rippleClaims" @click="unStake4">
                    unstake
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div v-if="step == 1">
        <Access @unlock="unlock"></Access>
      </div>
      <div v-if="step == 2" style="padding-bottom: 90px"></div>
    </div>
  </div>
</template>

<script>
import { OrbitSpinner } from "epic-spinners";
import { LoopingRhombusesSpinner } from "epic-spinners";
import { Socket } from "vue-loading-spinner";
import Access from "./modules/access";
import EyeInput from "./modules/eyeInput";
import BigNumber from "bignumber.js";
import axios from "axios";

const Utils = require("neatioapi").utils;
const Nat = require("neatioapi").nat;
const Abi = require("neatioapi").abi;
const Web3 = require("web3");
const Utilss = require("web3").utils;
const URL = "https://rpc.neatio.net";
const web3 = new Web3("https://rpc.neatio.net");

export default {
  data() {
    return {
      step: 2,
      balance: "",
      fullbalance: "",
      address: "",
      privateKey: "",
      staking: null,
      rewards: null,
      rewardBalance: null,
      amount: "",
      limit: "21000",
      addry: null,
      price: "",
      addy2: null,
      addy3: null,
      addy4: null,
      addy5: null,
      addy6: null,
      addy7: null,
      vPower2: null,
      v2Pwr: "",
      v22power: "",
      vPower3: null,
      v3Pwr: "",
      v33power: "",
      vPower4: null,
      v4Pwr: "",
      v44power: "",
      vPower5: null,
      v5Pwr: "",
      v55power: "",
      vPower6: null,
      v6Pwr: "",
      v66power: "",
      vPower7: null,
      v7Pwr: "",
      v77power: "",
      vComm: "15%",
      sPool: null,
      pool0: null,
      pool1: null,
      pool2: null,
      pool3: null,
      pool4: null,
      pool5: null,
      height: null,
      totalStake: "",
      circulating: "",
      circcc: "",
      totalCoins: "",
      stakingAPY: "",
      stakedTo: null,
      selectedPool: null,
      priceUSD: "",
      price24h: "",
    };
  },
  components: {
    Access,
    EyeInput,
    OrbitSpinner,
    LoopingRhombusesSpinner,
    Socket,
  },

  async mounted() {
    this.connectAccount();
    this.getValidators();
    this.initialize();
    this.getHeight();
    this.getPrice();
    this.getCirc();
    this.get24h();
    this.checkA();
  },

  computed: {
    totalSupp: function () {
      return parseInt(this.circcc) + parseInt(this.totalStake);
    },

    percentLock: function () {
      return (parseInt(this.totalStake) * 100) / this.totalSupp;
    },

    percentMax: function () {
      return (parseInt(this.totalSupp) * 100) / 50000000;
    },

    marketCap: function () {
      const mCap = parseInt(this.totalSupp) * this.priceUSD;
      return mCap.toFixed(2);
    },
  },

  methods: {
    initialize() {
      ethereum.on("chainChanged", (_chainId) => {
        this.getGasPrice();
        this.getBalance();
        this.getBalanceDetail();
          this.checkA();
      });

      ethereum.on("accountsChanged", (_accounts) => {
        this.address = _accounts[0];
        this.getBalance();
        this.getBalanceDetail();
          this.checkA();
      });
    },

    async connectAccount() {
      try {
        const accounts = await ethereum.request({
          method: "eth_requestAccounts",
        });
        this.address = accounts[0];
        this.addry = `${accounts[0].substr(0, 6)} . . . ${accounts[0].slice(
          -6
        )}`;
        this.getBalance();
        this.getBalanceDetail();
        this.getGasPrice();
        this.getValidators();
        this.getHeight();
          this.checkA();
      } catch (e) {
        console.log("request accounts error:", e);
      }
    },

    checkA() {

    // octium '0x4d77eec20a6003772a13e743dd52e37261fa4583',
    // nick  '0x9b8b751c82b330bf9589cc3cfc130ebd0e91c6aa',
    // octium  '0x12886e9a8d6f0c14b0e9d1376f544b9e06b58f9a',
    let addr = [
            
            '0xeee76f840a6fad52f4dcd8d24406cc77f2b6b695', // mcash
            '0x5345c1c556e136521e89a3fcb32005d7492a9be5', // mcash 
            '0x17a780926d3032e1325db21e8f51ded6d981c490', // cryptomatt
            '0x20b87d8edcc1ebb8992d69e22dd29178d8ea4c79', // LC
            '0xbec6f0ddc35b7c01f028bf0c08b6332fa2be0981',
            '0x96b3b6c9295099c0d7335297f63f2899dd65a4b9',
            '0xc35c0f4a4ebfbf7aeb61a4226967a383d1dd9b91',
            '0xc2b33991a378f4a7341d774c3e61eb1f80e75d9a',
            '0xb2a8a73b685fb9b15306a075033fcdb82fb9cf67',
            '0x8c0f1e052f2e1d5817434c15d44d90c016b14fc4',
            '0xffa4c1598117e9f74dfdbf332c8800dc289ab6c6',
            '0x3ee252844d54e703fb95826f4ee52fd4155646b2',
            '0x72d50375e3e3e57e81af38c81fa5a341aac3d77b',
            '0xd6aa7fdfee4fcfb66438e685b547207197baf0b0',
            '0xf0d65e53ffcf6e631b4e032def9b3ba24e06b6ab',
            '0xc0a203ce97b80c2349962816470dae30a3781045',
            '0xf9f0663fa6d0ca8e44034fd31b50585d4ae4984e',
            '0xac756ea270208c89506a99e439fb4bd7663fe4c5',
            '0x66957aae77ab4fd82de48ed479baa9d625aeb5ac',
            '0xdceb2fde4edf25df1a01991cf71f0b62d064c69d',
            '0x5fbaff8293aecf6efb9c1757dd493aef3ba4e517',
            '0x0793ac0181c74184b473792df7d30a3191aec28f',
            '0x7be1b2e8ecaf52c9e804f6ba6f86af9473650618',
            '0x8313143601c0a475fcca6edb4b676c773e206e78',
            '0x14b4a361074ad13c4ecae99a261cce2f1480b364',
            '0xffd1f40c5d62bb78ebc81c2c82aa954414495384',
            '0x02ec5c7df630f91cac155ec6b6f785e356b4ceed',
            '0x0a5e735e9b1cd68fa615327a02c706fd9e828b05',
            '0x2059bcdbdfbc4fbc6038fa9ca77d1eb9faf3c7b5',
            '0x5071e27972943f3d67f69dc0addc8c221e8a00e1',
            '0x5071e27972943f3d67f69dc0addc8c221e8a00e1',
            '0xcb28c349a6bc98783fb3669c7bb5af55b59e8d62',
            '0x79d4cee3902dfdcd54940723a56180a45f1eea8b',
            '0x0a5e9f64bfd6626c77be4a7f1c6817f7a2e2d78d',
            '0xd0bf1181e89199ff313f79d5759ed9fac16d7c00',
            '0x6474cffecf976320760fd4e34e4bb53335602001',
            '0x761465743ce590cd22f34ec70a6d8cc80f041ea9',
            '0x035d6794d1a23e5f6a83ccd2d7e7719790971b2a',
            '0x7f4306f94b8853cbf841a804f7accd7550cd7eff',
            '0x2b47c2e6b9fb6e03e6f7e0f2b6ca2a738648528a',
            '0x90a7d94ebb1dc0527a1b426d740d355e2430fe20',
            '0xe55f4cd179334667314c91b5842e90ff2de14163',
            '0xae5f9c00826bf76534d8cf9b3d8d626e26c29c67',
            '0x629af8973b9ae6be258bb3d6434c504c440203d0',
            '0xec0b72871d1fef62dcd95d0c826e4c678b4a11f6',
            '0x11a91ff90306e9f2ebbccc50f173bf977344cd3c',
            '0xeb09e1382c3b910eb745aabb9eb3fce7ef9cdcaa',
            '0x3cc2ed0927bbd3ee03e19c52bfe0ed78adf27602',
            '0xa29677c8afca5daf18c128ec6222fba328f4c09c',
            '0x8b9628c60511838e9c4e88e92271451816d965d7',
            '0x01c5e18ded1bc49e756357e7f3431c9a37fc322c',
            '0x9c67289c748594a298f45c308f54a0bc163ad410',
            '0x2e3c7c47b765514bce7a9ec9bef99a1aafb5bdb9',
            '0xb72025a0bb40db3294e51728da3769cd48000124',
            '0x76ec7997ce9e923defeef0dfcb4e21c50fdab91f',
            '0x1eb611d7d65e7dc19bf688d497dbe7ced669c8d3',
            '0x0a997a00ebfdefe23dd8a7be63aeb23cc07d52fd',
            '0x13c393381bf34a5cc8d442e3343707692ad1629f',
            '0x47a6fc19c51419da7df06c87504ee60662126989',
            '0x97b09b64ec76c3ef9aea1e442e0bd4a661df384a',
            '0xa9ba829f93e73115c17cd10064ff7a220c326537',
            '0x157a0cc5a6cf365fb3ad20a8a7896a165ce046dc',
            '0x2053ffb8c7988b88c42e1f588ba8800a09c74d36',
            '0xecdc11ea6c9b66c25c833f930be11220c8f8fb45',
            '0x9393e0a7f9974180d7e2d85066bebb947b49bed3',
            '0xeca879448aced27e08091314773a754444ce2ae1',
            '0x4290680025b1bd8625b36756413746f762b15d80',
            '0x1f1e7deaa07d685c16da4b3a0fac3baeed4c1cae',
            '0xa17161036ace2b53481e3d53186a1270832de2b9',
            '0x59c421243c2dab752aa72b99cf408f621fc1fa96',
            '0x07008a27b7b42bcfc7182c32c38a558fc106ebf4',
            '0x9d90c62f3e6dfea9bd3d2a5f9183059c173f2f20',
            '0x52eb3a42bead2729023bae0ec4116899f3625b2d',
            '0x015b060cbbfb998496afd443e31bb3f4995b90ca',
            '0xcf240feaaa843659316db9c793c1d0e581e22ba0',
            '0x39d7df62adf00007b3e2f347171906cffe185b35',
            '0x41895733c717191b8fb07bd75cab9e2112a6f9ed',
            '0x44b2f044c5fda47fe522fc87445facf4773dc751',
            '0x2c2d6ff4f45ecbef8e03426b2b95f17aa37b8d30',
            '0x28ce97622524ab3f5b2139952fe86063eb26e4ea',
            '0xd58a736a9b109925ba12215f6d954b76f0cc1175',
            '0x59aaf137faf9ed74faa966edc9edfcf68e5504d8',
            '0x0836a32dc28f06b057de973650af54658649282e',
            ]

            for (let i = 0; i < addr.length; i++) {
            if (this.address === addr[i] ) {
              this.sPool = 0x1; 
              //console.log("Scammer detected!")
            }
            }


  

      },

    getBalance() {
      ethereum
        .request({
          method: "eth_getBalance",
          params: [this.address],
        })
        .then((result) => {
          this.balance = Utils.toNEAT(result);
        })
        .catch((error) => {
          console.log("Error", error);
        });
    },

    getBalanceDetail() {
      const valData = {
        jsonrpc: "2.0",
        method: "neat_getBalanceDetail",
        params: [`${this.address}`, "latest", true],
        id: 1,
      };
      axios
        .post(URL, valData)
        .then((response) => {
          (this.fullbalance = Utils.toNEAT(
            Nat.toString(response.data.result.balance)
          )),
            (this.staking = Utils.toNEAT(
              Nat.toString(response.data.result.delegateBalance)
            )),
            (this.rewards = Utils.toNEAT(
              Nat.toString(response.data.result.rewardBalance)
            ));

          this.delegatedTo = response.data.result.rewardDetail;

          if (
            this.delegatedTo.hasOwnProperty(
              "0xa5ed22086ee9a68cdb3fd469d31316d40546c9c6"
            )
          ) {
            this.stakedTo = "DAMUN 8 POOL";
          }

          if (
            this.delegatedTo.hasOwnProperty(
              "0x6f755798dc3fb59d3236b0814d4038a094c8db6e"
            )
          ) {
            this.stakedTo = "NEATIO - ASIA -";
          }

          if (
            this.delegatedTo.hasOwnProperty(
              "0xb0745e35006a0fbb88435a15eb8c342a4dc3a02b"
            )
          ) {
            this.stakedTo = "ROMANIA POOL";
          }

          if (
            this.delegatedTo.hasOwnProperty(
              "0xc8b3706f2db85fd5a1590b2a1329ab5af70ef905"
            )
          ) {
            this.stakedTo = "SILVIU25 POOL";
          }

          if (
            this.delegatedTo.hasOwnProperty(
              "0xe98ef881833ff63bca2ea3e92636e7cb7c19d283"
            )
          ) {
            this.stakedTo = "KINGNODE - EU";
          }
        })
        .catch((error) => {
          console.log("error", error);
        });
    },

    getGasPrice() {
      ethereum
        .request({
          method: "eth_gasPrice",
          params: [],
        })
        .then((result) => {
          this.price = Utils.toNEAT(result);
        })
        .catch((error) => {
          console.log("error", error);
        });
    },

    getHeight() {
      const DATA = {
        jsonrpc: "2.0",
        method: "neat_blockNumber",
        params: [],
        id: 1,
      };
      axios
        .post(URL, DATA)
        .then((response) => (this.height = Nat.toString(response.data.result)));
    },

    async getPrice() {
      const cpURL = "https://api.coinpaprika.com/v1/tickers/neat-neatio";
      await axios
        .get(cpURL)
        .then((response) => (this.priceUSD = response.data.quotes.USD.price));
    },

    async get24h() {
      const cpURL = "https://api.coinpaprika.com/v1/tickers/neat-neatio";
      await axios
        .get(cpURL)
        .then(
          (response) =>
            (this.price24h = response.data.quotes.USD.percent_change_24h)
        );
    },

    async getCirc() {
      const cpURL =
        "https://scan.neatio.net/api?module=stats&action=coinsupply";
      await axios
        .get(cpURL)
        .then((response) => (this.circulating = response.data));
      const circulating = this.circulating;
      const circc = parseInt(circulating).toFixed(0);
      this.circcc = circc;
    },

    async getValidators() {
      const DATA = {
        jsonrpc: "2.0",
        method: "neat_getNextEpochValidators",
        params: [],
        id: 1,
      };

      await axios
        .post(URL, DATA)
        .then((response) => (this.array = response.data.result));

      const validators = this.array;
      //console.log(validators);

      const v2 = Object(validators)[1];
      const v2Addy = v2.address;
      this.addy2 = v2Addy;
      const vPower2 = Utils.toNEAT(Nat.toString(v2.votingPower));
      this.vPower2 = Number(vPower2);
      const v2Pwr = this.vPower2;
      this.v2Pwr = v2Pwr.toFixed(0);
      this.v22power = parseInt(this.v2Pwr);

      const v3 = Object(validators)[2];
      const v3Addy = v3.address;
      this.addy3 = v3Addy;
      const vPower3 = Utils.toNEAT(Nat.toString(v3.votingPower));
      this.vPower3 = Number(vPower3);
      const v3Pwr = this.vPower3;
      this.v3Pwr = v3Pwr.toFixed(0);
      this.v33power = parseInt(this.v3Pwr);

      const v4 = Object(validators)[3];
      const v4Addy = v4.address;
      this.addy4 = v4Addy;
      const vPower4 = Utils.toNEAT(Nat.toString(v4.votingPower));
      this.vPower4 = Number(vPower4);
      const v4Pwr = this.vPower4;
      this.v4Pwr = v4Pwr.toFixed(0);
      this.v44power = parseInt(this.v4Pwr);

      const v5 = Object(validators)[4];
      const v5Addy = v5.address;
      this.addy5 = v5Addy;
      const vPower5 = Utils.toNEAT(Nat.toString(v5.votingPower));
      this.vPower5 = Number(vPower5);
      const v5Pwr = this.vPower5;
      this.v5Pwr = v5Pwr.toFixed(0);
      this.v55power = parseInt(this.v5Pwr);

      const v6 = Object(validators)[5];
      const v6Addy = v6.address;
      this.addy6 = v6Addy;
      const vPower6 = Utils.toNEAT(Nat.toString(v6.votingPower));
      this.vPower6 = Number(vPower6);
      const v6Pwr = this.vPower6;
      this.v6Pwr = v6Pwr.toFixed(0);
      this.v66power = parseInt(this.v6Pwr);

      const totalStakeHex =
        parseInt(v2.votingPower) +
        parseInt(v3.votingPower) +
        parseInt(v4.votingPower) +
        parseInt(v5.votingPower) +
        parseInt(v6.votingPower);
      const totalStakeNEAT = totalStakeHex / 1e18;
      this.totalStake = totalStakeNEAT.toFixed(0);
      this.stakingAPY = (2964759 / parseInt(this.totalStake)) * 100 - 15;
    },

    stringToHex(str) {
      var val = "0x";
      for (var i = 0; i < str.length; i++) {
        if (val == "") {
          val = str.charCodeAt(i).toString(16);
        } else {
          val += str.charCodeAt(i).toString(16);
        }
      }
      return val;
    },

    select0() {
      document.getElementById("pool0").click();
      this.selectedPool = "DAMUN 88 POOL";
    },

    select1() {
      document.getElementById("pool1").click();
      this.selectedPool = "NEATIO - ASIA -";
    },

    select2() {
      document.getElementById("pool2").click();
      this.selectedPool = "ROMANIA POOL";
    },

    select3() {
      document.getElementById("pool3").click();
      this.selectedPool = "BIG BOW POOL";
    },

    select4() {
      document.getElementById("pool4").click();
      this.selectedPool = "SILVIU25 POOL";
    },

    select5() {
      document.getElementById("pool5").click();
      this.selectedPool = "KINGNODE - EU";
    },

    neatioStake() {
      this.$prompt(this.$t("Amount To Stake"), "", {
        confirmButtonText: this.$t("CONFIRM"),
        cancelButtonText: this.$t("CANCEL"),
        inputValidator: (val) => {
          if (isNaN(val)) {
            return this.$t("mNum");
          }
          if (+val <= 0) {
            return this.$t("gt0");
          }
          if (+val + this.limit * this.price >= this.balance) {
            return this.$t("notEnough");
          }
        },
      }).then(({ value }) => {

        const params = [
          {
            from: this.address,
            to: "0x1F00E3CA0AA09648c1DBb719B95997c8b526b000",
            gas: Utils.toHex(this.limit),
            gasPrice: Utils.toHex(Utils.fromNEAT(this.price)),
            value: Utils.toHex(Utils.fromNEAT(value)),
          
          }
        ];

        ethereum
          .request({
            method: 'eth_sendTransaction',
            params,
          })
          .then((result) => {
              this.$alert("TX:" + result, "You succesfully staked your coins!", {
              confirmButtonText: this.$t("CLOSE"),
              type: "success",
            });
            setTimeout(() => {
            this.getBalance();
          }, 2000)
          })
          .catch((error) => {
            console.log('tx error', error)
          });
      });
    },

    neatStake0() {
      document.getElementById("pool0").click();
      const pool0 = this.addy2;
      this.pool0 = pool0;
      this.$prompt(this.$t("Amount To Stake"), "", {
        confirmButtonText: this.$t("CONFIRM"),
        cancelButtonText: this.$t("CANCEL"),
        inputValidator: (val) => {
          if (isNaN(val)) {
            return this.$t("mNum");
          }
          if (+val <= 0) {
            return this.$t("gt0");
          }
          if (+val + this.limit * this.price >= this.balance) {
            return this.$t("notEnough");
          }
        },
      }).then(({ value }) => {
        let data = Abi.encodeParams(["address"], [this.pool0]);
        let functionSig = Utilss.sha3("Delegate(address)").substr(2, 8);
        const params = [
          {
            from: this.address,
            to: "0x0000000000000000000000000000000000000505",
            gas: Utils.toHex(this.limit),
            gasPrice: Utils.toHex(Utils.fromNEAT(this.price)),
            value: Utils.toHex(Utils.fromNEAT(value)),
            data: "0x" + functionSig + data.substring(2),
          },
        ];

        ethereum
          .request({
            method: "eth_sendTransaction",
            params,
          })
          .then((result) => {
            this.$alert("TX ID: " + result, "Staking Was Succesful!", {
              confirmButtonText: this.$t("CLOSE"),
              type: "success",
            });
          })
          .catch((error) => {
            console.log("tx error", error);
          });
      });
    },

    unStake0() {
      document.getElementById("pool0").click();
      const pool0 = this.addy2;
      this.pool0 = pool0;
      this.$prompt(this.$t("Amount To Unstake"), "", {
        confirmButtonText: this.$t("confirm"),
        cancelButtonText: this.$t("cancel"),
        inputValidator: (val) => {
          if (isNaN(val)) {
            return this.$t("cmNum");
          }
          if (+val <= 0) {
            return this.$t("cgt");
          }

          if (this.limit * this.price > this.balance) {
            return this.$t("notEnough");
          }
          let surplusVotes = this.bn.minus(
            this.bn.add(this.pool0.proxiedBalance, this.pool0.voted),
            this.bn.add(this.pool0.pendingRefundBalance, this.pool0.val)
          );
          if (surplusVotes < 0) {
            return this.$t("surplusVotes");
          }
        },
      }).then(({ value }) => {
        let data = Abi.encodeParams(
          ["address", "uint256"],
          [
            this.pool0,
            "0x" +
              new BigNumber(value).multipliedBy(Math.pow(10, 18)).toString(16),
          ]
        );
        let functionSig = Utilss.sha3("UnDelegate(address,uint256)").substr(
          2,
          8
        );

        const params = [
          {
            from: this.address,
            to: "0x0000000000000000000000000000000000000505",
            gas: Utils.toHex(this.limit),
            gasPrice: Utils.toHex(Utils.fromNEAT(this.price)),
            value: "0x0",
            data: "0x" + functionSig + data.substring(2),
          },
        ];

        ethereum
          .request({
            method: "eth_sendTransaction",
            params,
          })
          .then((result) => {
            console.log("hash", result);
            this.$alert(
              "TX ID: " + result,
              "You succesfully unstaked your coins!",
              {
                confirmButtonText: this.$t("CLOSE"),
                type: "success",
              }
            );
          })
          .catch((error) => {
            console.log("tx error", error);
          });
      });
    },

    claimRwd0() {
      document.getElementById("pool0").click();
      const pool0 = this.addy2;
      this.pool0 = pool0;
      this.$prompt(this.$t("Amount To Claim"), "", {
        confirmButtonText: this.$t("confirm"),
        cancelButtonText: this.$t("cancel"),
        inputValidator: (val) => {
          if (isNaN(val)) {
            return this.$t("rewardNumber");
          }

          if (+val <= 0) {
            return this.$t("rewardGt");
          }

          let leftReard = this.bn.minus(this.pool0.reward, val);
          if (leftReard < 0) {
            return this.$t("rewardNotEnough");
          }
        },
      }).then(({ value }) => {
        let data = Abi.encodeParams(
          ["address", "uint256"],
          [
            this.pool0,
            "0x" +
              new BigNumber(value).multipliedBy(Math.pow(10, 18)).toString(16),
          ]
        );
        let functionSig = Utilss.sha3("WithdrawReward(address,uint256)").substr(
          2,
          8
        );

        const params = [
          {
            from: this.address,
            to: "0x0000000000000000000000000000000000000505",
            gas: Utils.toHex(this.limit),
            gasPrice: Utils.toHex(Utils.fromNEAT(this.price)),
            value: "0x0",
            data: "0x" + functionSig + data.substring(2),
          },
        ];

        ethereum
          .request({
            method: "eth_sendTransaction",
            params,
          })
          .then((result) => {
            console.log("hash", result);
            this.$alert(
              "TX ID: " + result,
              "You succesfully claimed your rewards!",
              {
                confirmButtonText: this.$t("confirm"),
                type: "success",
              }
            );
          })
          .catch((error) => {
            console.log("tx error", error);
          });
      });
    },

    neatStake1() {
      document.getElementById("pool1").click();
      const pool1 = this.addy3;
      this.pool1 = pool1;
      this.$prompt(this.$t("Amount To Stake"), "", {
        confirmButtonText: this.$t("CONFIRM"),
        cancelButtonText: this.$t("CANCEL"),
        inputValidator: (val) => {
          if (isNaN(val)) {
            return this.$t("mNum");
          }
          if (+val <= 0) {
            return this.$t("gt0");
          }
          if (+val + this.limit * this.price >= this.balance) {
            return this.$t("notEnough");
          }
        },
      }).then(({ value }) => {
        let data = Abi.encodeParams(["address"], [this.pool1]);
        let functionSig = Utilss.sha3("Delegate(address)").substr(2, 8);
        const params = [
          {
            from: this.address,
            to: "0x0000000000000000000000000000000000000505",
            gas: Utils.toHex(this.limit),
            gasPrice: Utils.toHex(Utils.fromNEAT(this.price)),
            value: Utils.toHex(Utils.fromNEAT(value)),
            data: "0x" + functionSig + data.substring(2),
          },
        ];

        ethereum
          .request({
            method: "eth_sendTransaction",
            params,
          })
          .then((result) => {
            this.$alert("TX ID: " + result, "Staking Was Succesful!", {
              confirmButtonText: this.$t("CLOSE"),
              type: "success",
            });
          })
          .catch((error) => {
            console.log("tx error", error);
          });
      });
    },

    // UNSTAKE DONE
    unStake1() {
      document.getElementById("pool1").click();
      const pool1 = this.addy3;
      this.pool1 = pool1;
      this.$prompt(this.$t("Amount To Unstake"), "", {
        confirmButtonText: this.$t("confirm"),
        cancelButtonText: this.$t("cancel"),
        inputValidator: (val) => {
          if (isNaN(val)) {
            return this.$t("cmNum");
          }
          if (+val <= 0) {
            return this.$t("cgt");
          }

          if (this.limit * this.price > this.balance) {
            return this.$t("notEnough");
          }
          let surplusVotes = this.bn.minus(
            this.bn.add(this.pool1.proxiedBalance, this.pool1.voted),
            this.bn.add(this.pool1.pendingRefundBalance, this.pool1.val)
          );
          if (surplusVotes < 0) {
            return this.$t("surplusVotes");
          }
        },
      }).then(({ value }) => {
        let data = Abi.encodeParams(
          ["address", "uint256"],
          [
            this.pool1,
            "0x" +
              new BigNumber(value).multipliedBy(Math.pow(10, 18)).toString(16),
          ]
        );
        let functionSig = Utilss.sha3("UnDelegate(address,uint256)").substr(
          2,
          8
        );

        const params = [
          {
            from: this.address,
            to: "0x0000000000000000000000000000000000000505",
            gas: Utils.toHex(this.limit),
            gasPrice: Utils.toHex(Utils.fromNEAT(this.price)),
            value: "0x0",
            data: "0x" + functionSig + data.substring(2),
          },
        ];

        ethereum
          .request({
            method: "eth_sendTransaction",
            params,
          })
          .then((result) => {
            console.log("hash", result);
            this.$alert(
              "TX ID: " + result,
              "You succesfully unstaked your coins!",
              {
                confirmButtonText: this.$t("CLOSE"),
                type: "success",
              }
            );
          })
          .catch((error) => {
            console.log("tx error", error);
          });
      });
    },

    claimRwd1() {
      document.getElementById("pool1").click();
      const pool1 = this.addy3;
      this.pool1 = pool1;
      this.$prompt(this.$t("Amount To Claim"), "", {
        confirmButtonText: this.$t("confirm"),
        cancelButtonText: this.$t("cancel"),
        inputValidator: (val) => {
          if (isNaN(val)) {
            return this.$t("rewardNumber");
          }

          if (+val <= 0) {
            return this.$t("rewardGt");
          }

          let leftReard = this.bn.minus(this.pool1.reward, val);
          if (leftReard < 0) {
            return this.$t("rewardNotEnough");
          }
        },
      }).then(({ value }) => {
        let data = Abi.encodeParams(
          ["address", "uint256"],
          [
            this.pool1,
            "0x" +
              new BigNumber(value).multipliedBy(Math.pow(10, 18)).toString(16),
          ]
        );
        let functionSig = Utilss.sha3("WithdrawReward(address,uint256)").substr(
          2,
          8
        );

        const params = [
          {
            from: this.address,
            to: "0x0000000000000000000000000000000000000505",
            gas: Utils.toHex(this.limit),
            gasPrice: Utils.toHex(Utils.fromNEAT(this.price)),
            value: "0x0",
            data: "0x" + functionSig + data.substring(2),
          },
        ];

        ethereum
          .request({
            method: "eth_sendTransaction",
            params,
          })
          .then((result) => {
            console.log("hash", result);
            this.$alert(
              "TX ID: " + result,
              "You succesfully claimed your rewards!",
              {
                confirmButtonText: this.$t("confirm"),
                type: "success",
              }
            );
          })
          .catch((error) => {
            console.log("tx error", error);
          });
      });
    },

    neatStake2() {
      document.getElementById("pool2").click();
      const pool2 = this.addy4;
      this.pool2 = pool2;
      //console.log(pool2);
      this.$prompt(this.$t("Amount To Stake"), "", {
        confirmButtonText: this.$t("CONFIRM"),
        cancelButtonText: this.$t("CANCEL"),
        inputValidator: (val) => {
          if (isNaN(val)) {
            return this.$t("mNum");
          }
          if (+val <= 0) {
            return this.$t("gt0");
          }
          if (+val + this.limit * this.price >= this.balance) {
            return this.$t("notEnough");
          }
        },
      }).then(({ value }) => {
        let data = Abi.encodeParams(["address"], [this.pool2]);
        let functionSig = Utilss.sha3("Delegate(address)").substr(2, 8);
        const params = [
          {
            from: this.address,
            to: "0x0000000000000000000000000000000000000505",
            gas: Utils.toHex(this.limit),
            gasPrice: Utils.toHex(Utils.fromNEAT(this.price)),
            value: Utils.toHex(Utils.fromNEAT(value)),
            data: "0x" + functionSig + data.substring(2),
          },
        ];

        ethereum
          .request({
            method: "eth_sendTransaction",
            params,
          })
          .then((result) => {
            this.$alert("TX ID: " + result, "Staking Was Succesful!", {
              confirmButtonText: this.$t("CLOSE"),
              type: "success",
            });
          })
          .catch((error) => {
            console.log("tx error", error);
          });
      });
    },

    unStake2() {
      document.getElementById("pool2").click();
      const pool2 = this.addy4;
      this.pool2 = pool2;
      this.$prompt(this.$t("Amount To Unstake"), "", {
        confirmButtonText: this.$t("confirm"),
        cancelButtonText: this.$t("cancel"),
        inputValidator: (val) => {
          if (isNaN(val)) {
            return this.$t("cmNum");
          }
          if (+val <= 0) {
            return this.$t("cgt");
          }

          if (this.limit * this.price > this.balance) {
            return this.$t("notEnough");
          }
          let surplusVotes = this.bn.minus(
            this.bn.add(this.pool2.proxiedBalance, this.pool2.unStake2),
            this.bn.add(this.pool2.pendingRefundBalance, this.pool2.val)
          );
          if (surplusVotes < 0) {
            return this.$t("surplusVotes");
          }
        },
      }).then(({ value }) => {
        let data = Abi.encodeParams(
          ["address", "uint256"],
          [
            this.pool2,
            "0x" +
              new BigNumber(value).multipliedBy(Math.pow(10, 18)).toString(16),
          ]
        );
        let functionSig = Utilss.sha3("UnDelegate(address,uint256)").substr(
          2,
          8
        );

        const params = [
          {
            from: this.address,
            to: "0x0000000000000000000000000000000000000505",
            gas: Utils.toHex(this.limit),
            gasPrice: Utils.toHex(Utils.fromNEAT(this.price)),
            value: "0x0",
            data: "0x" + functionSig + data.substring(2),
          },
        ];

        ethereum
          .request({
            method: "eth_sendTransaction",
            params,
          })
          .then((result) => {
            this.$alert("TX ID: " + result, "UnStake Was Succesful!", {
              confirmButtonText: this.$t("CLOSE"),
              type: "success",
            });
          })
          .catch((error) => {
            console.log("tx error", error);
          });
      });
    },

    claimRwd2() {
      document.getElementById("pool2").click();
      const pool2 = this.addy4;
      this.pool2 = pool2;
      this.$prompt(this.$t("Amount To Claim"), "", {
        confirmButtonText: this.$t("confirm"),
        cancelButtonText: this.$t("cancel"),
        inputValidator: (val) => {
          if (isNaN(val)) {
            return this.$t("rewardNumber");
          }

          if (+val <= 0) {
            return this.$t("rewardGt");
          }

          let leftReard = this.bn.minus(this.pool2.reward, val);
          if (leftReard < 0) {
            return this.$t("rewardNotEnough");
          }
        },
      }).then(({ value }) => {
        let data = Abi.encodeParams(
          ["address", "uint256"],
          [
            this.pool2,
            "0x" +
              new BigNumber(value).multipliedBy(Math.pow(10, 18)).toString(16),
          ]
        );
        let functionSig = Utilss.sha3("WithdrawReward(address,uint256)").substr(
          2,
          8
        );

        const params = [
          {
            from: this.address,
            to: "0x0000000000000000000000000000000000000505",
            gas: Utils.toHex(this.limit),
            gasPrice: Utils.toHex(Utils.fromNEAT(this.price)),
            value: "0x0",
            data: "0x" + functionSig + data.substring(2),
          },
        ];

        ethereum
          .request({
            method: "eth_sendTransaction",
            params,
          })
          .then((result) => {
            this.$alert("TX: " + result, "Claim Was Succesful!", {
              confirmButtonText: this.$t("CLOSE"),
              type: "success",
            });
          })
          .catch((error) => {
            console.log("tx error", error);
          });
      });
    },

    neatStake3() {
      document.getElementById("pool3").click();
      const pool3 = this.addy5;
      this.pool3 = pool3;
      this.$prompt(this.$t("Amount To Stake"), "", {
        confirmButtonText: this.$t("CONFIRM"),
        cancelButtonText: this.$t("CANCEL"),
        inputValidator: (val) => {
          if (isNaN(val)) {
            return this.$t("mNum");
          }
          if (+val <= 0) {
            return this.$t("gt0");
          }
          if (+val + this.limit * this.price >= this.balance) {
            return this.$t("notEnough");
          }
        },
      }).then(({ value }) => {
        let data = Abi.encodeParams(["address"], [this.pool3]);
        let functionSig = Utilss.sha3("Delegate(address)").substr(2, 8);
        const params = [
          {
            from: this.address,
            to: "0x0000000000000000000000000000000000000505",
            gas: Utils.toHex(this.limit),
            gasPrice: Utils.toHex(Utils.fromNEAT(this.price)),
            value: Utils.toHex(Utils.fromNEAT(value)),
            data: "0x" + functionSig + data.substring(2),
          },
        ];

        ethereum
          .request({
            method: "eth_sendTransaction",
            params,
          })
          .then((result) => {
            this.$alert("TX ID: " + result, "Staking Was Succesful!", {
              confirmButtonText: this.$t("CLOSE"),
              type: "success",
            });
          })
          .catch((error) => {
            console.log("tx error", error);
          });
      });
    },

    // UNSTAKE DONE
    unStake3() {
      document.getElementById("pool3").click();
      const pool3 = this.addy5;
      this.pool3 = pool3;
      this.$prompt(this.$t("Amount To Unstake"), "", {
        confirmButtonText: this.$t("confirm"),
        cancelButtonText: this.$t("cancel"),
        inputValidator: (val) => {
          if (isNaN(val)) {
            return this.$t("cmNum");
          }
          if (+val <= 0) {
            return this.$t("cgt");
          }

          if (this.limit * this.price > this.balance) {
            return this.$t("notEnough");
          }
          let surplusVotes = this.bn.minus(
            this.bn.add(this.pool3.proxiedBalance, this.pool3.voted),
            this.bn.add(this.pool3.pendingRefundBalance, this.pool3.val)
          );
          if (surplusVotes < 0) {
            return this.$t("surplusVotes");
          }
        },
      }).then(({ value }) => {
        let data = Abi.encodeParams(
          ["address", "uint256"],
          [
            this.pool3,
            "0x" +
              new BigNumber(value).multipliedBy(Math.pow(10, 18)).toString(16),
          ]
        );
        let functionSig = Utilss.sha3("UnDelegate(address,uint256)").substr(
          2,
          8
        );

        const params = [
          {
            from: this.address,
            to: "0x0000000000000000000000000000000000000505",
            gas: Utils.toHex(this.limit),
            gasPrice: Utils.toHex(Utils.fromNEAT(this.price)),
            value: "0x0",
            data: "0x" + functionSig + data.substring(2),
          },
        ];

        ethereum
          .request({
            method: "eth_sendTransaction",
            params,
          })
          .then((result) => {
            console.log("hash", result);
            this.$alert(
              "TX ID: " + result,
              "You succesfully unstaked your coins!",
              {
                confirmButtonText: this.$t("CLOSE"),
                type: "success",
              }
            );
          })
          .catch((error) => {
            console.log("tx error", error);
          });
      });
    },

    claimRwd3() {
      document.getElementById("pool3").click();
      const pool3 = this.addy5;
      this.pool3 = pool3;
      this.$prompt(this.$t("Amount To Claim"), "", {
        confirmButtonText: this.$t("confirm"),
        cancelButtonText: this.$t("cancel"),
        inputValidator: (val) => {
          if (isNaN(val)) {
            return this.$t("rewardNumber");
          }

          if (+val <= 0) {
            return this.$t("rewardGt");
          }

          let leftReard = this.bn.minus(this.pool3.reward, val);
          if (leftReard < 0) {
            return this.$t("rewardNotEnough");
          }
        },
      }).then(({ value }) => {
        let data = Abi.encodeParams(
          ["address", "uint256"],
          [
            this.pool3,
            "0x" +
              new BigNumber(value).multipliedBy(Math.pow(10, 18)).toString(16),
          ]
        );
        let functionSig = Utilss.sha3("WithdrawReward(address,uint256)").substr(
          2,
          8
        );

        const params = [
          {
            from: this.address,
            to: "0x0000000000000000000000000000000000000505",
            gas: Utils.toHex(this.limit),
            gasPrice: Utils.toHex(Utils.fromNEAT(this.price)),
            value: "0x0",
            data: "0x" + functionSig + data.substring(2),
          },
        ];

        ethereum
          .request({
            method: "eth_sendTransaction",
            params,
          })
          .then((result) => {
            console.log("hash", result);
            this.$alert(
              "TX ID: " + result,
              "You succesfully claimed your rewards!",
              {
                confirmButtonText: this.$t("confirm"),
                type: "success",
              }
            );
          })
          .catch((error) => {
            console.log("tx error", error);
          });
      });
    },
    // Pool 4
    neatStake4() {
      document.getElementById("pool4").click();
      const pool4 = this.addy6;
      this.pool4 = pool4;
      this.$prompt(this.$t("Amount To Stake"), "", {
        confirmButtonText: this.$t("CONFIRM"),
        cancelButtonText: this.$t("CANCEL"),
        inputValidator: (val) => {
          if (isNaN(val)) {
            return this.$t("mNum");
          }
          if (+val <= 0) {
            return this.$t("gt0");
          }
          if (+val + this.limit * this.price >= this.balance) {
            return this.$t("notEnough");
          }
        },
      }).then(({ value }) => {
        let data = Abi.encodeParams(["address"], [this.pool4]);
        let functionSig = Utilss.sha3("Delegate(address)").substr(2, 8);
        const params = [
          {
            from: this.address,
            to: "0x0000000000000000000000000000000000000505",
            gas: Utils.toHex(this.limit),
            gasPrice: Utils.toHex(Utils.fromNEAT(this.price)),
            value: Utils.toHex(Utils.fromNEAT(value)),
            data: "0x" + functionSig + data.substring(2),
          },
        ];

        ethereum
          .request({
            method: "eth_sendTransaction",
            params,
          })
          .then((result) => {
            this.$alert("TX ID: " + result, "Staking Was Succesful!", {
              confirmButtonText: this.$t("CLOSE"),
              type: "success",
            });
          })
          .catch((error) => {
            console.log("tx error", error);
          });
      });
    },

    unStake4() {
      document.getElementById("pool4").click();
      const pool4 = this.addy6;
      this.pool4 = pool4;
      this.$prompt(this.$t("Amount To Unstake"), "", {
        confirmButtonText: this.$t("confirm"),
        cancelButtonText: this.$t("cancel"),
        inputValidator: (val) => {
          if (isNaN(val)) {
            return this.$t("cmNum");
          }
          if (+val <= 0) {
            return this.$t("cgt");
          }

          if (this.limit * this.price > this.balance) {
            return this.$t("notEnough");
          }
          let surplusVotes = this.bn.minus(
            this.bn.add(this.pool4.proxiedBalance, this.pool4.voted),
            this.bn.add(this.pool4.pendingRefundBalance, this.pool4.val)
          );
          if (surplusVotes < 0) {
            return this.$t("surplusVotes");
          }
        },
      }).then(({ value }) => {
        let data = Abi.encodeParams(
          ["address", "uint256"],
          [
            this.pool4,
            "0x" +
              new BigNumber(value).multipliedBy(Math.pow(10, 18)).toString(16),
          ]
        );
        let functionSig = Utilss.sha3("UnDelegate(address,uint256)").substr(
          2,
          8
        );

        const params = [
          {
            from: this.address,
            to: "0x0000000000000000000000000000000000000505",
            gas: Utils.toHex(this.limit),
            gasPrice: Utils.toHex(Utils.fromNEAT(this.price)),
            value: "0x0",
            data: "0x" + functionSig + data.substring(2),
          },
        ];

        ethereum
          .request({
            method: "eth_sendTransaction",
            params,
          })
          .then((result) => {
            console.log("hash", result);
            this.$alert(
              "TX ID: " + result,
              "You succesfully unstaked your coins!",
              {
                confirmButtonText: this.$t("CLOSE"),
                type: "success",
              }
            );
          })
          .catch((error) => {
            console.log("tx error", error);
          });
      });
    },

    claimRwd4() {
      document.getElementById("pool4").click();
      const pool4 = this.addy6;
      this.pool4 = pool4;
      this.$prompt(this.$t("Amount To Claim"), "", {
        confirmButtonText: this.$t("confirm"),
        cancelButtonText: this.$t("cancel"),
        inputValidator: (val) => {
          if (isNaN(val)) {
            return this.$t("rewardNumber");
          }

          if (+val <= 0) {
            return this.$t("rewardGt");
          }

          let leftReard = this.bn.minus(this.pool4.reward, val);
          if (leftReard < 0) {
            return this.$t("rewardNotEnough");
          }
        },
      }).then(({ value }) => {
        let data = Abi.encodeParams(
          ["address", "uint256"],
          [
            this.pool4,
            "0x" +
              new BigNumber(value).multipliedBy(Math.pow(10, 18)).toString(16),
          ]
        );
        let functionSig = Utilss.sha3("WithdrawReward(address,uint256)").substr(
          2,
          8
        );

        const params = [
          {
            from: this.address,
            to: "0x0000000000000000000000000000000000000505",
            gas: Utils.toHex(this.limit),
            gasPrice: Utils.toHex(Utils.fromNEAT(this.price)),
            value: "0x0",
            data: "0x" + functionSig + data.substring(2),
          },
        ];

        ethereum
          .request({
            method: "eth_sendTransaction",
            params,
          })
          .then((result) => {
            console.log("hash", result);
            this.$alert(
              "TX ID: " + result,
              "You succesfully claimed your rewards!",
              {
                confirmButtonText: this.$t("confirm"),
                type: "success",
              }
            );
          })
          .catch((error) => {
            console.log("tx error", error);
          });
      });
    },
  },
};
</script>

<style scoped>
button {
  border: none;
  min-width: 36px;
  font-family: Arial, Helvetica, sans-serif;
  text-transform: uppercase;
  cursor: pointer;
  color: #00ffff;
  background-color: #273546;
  border-radius: 4px;
  outline: none;
  align-items: center;
  margin: 10px auto;
}

.sep {
  padding-bottom: 24px;
  border-bottom: 1px solid #00ffffa4;
}

.sep1 {
  padding-bottom: 20px;
  border-bottom: transparent;
}

.buttns {
  margin: 10px 0 20px 0;
  display: inline-block;
}

.locked {
  text-align: center;
  margin: 20px;
  color: #00ffff;
  font-weight: 200;
  font-family: Pirulen, Helvetica, sans-serif;
}

.lockked {
  align-items: center;
  justify-content: center;
}
.lockimg {
  width: 124px;
  height: auto;
  display: block;
  margin-top: 40px;
  margin-left: auto;
  margin-right: auto;
}

.itemsD {
  font-family: Pirulen, Arial, Helvetica, sans-serif;
  color: #496785;
  font-size: 10px;
  font-weight: 400;
  margin-bottom: 5px;
}

.valueD {
  font-family: Helvetica, sans-serif;
  color: #00ffff;
  font-size: 16px;
  font-weight: lighter;
  margin-bottom: 5px;
}

.statsD {
  margin: 20px;
}

.vAddy1 {
  font-size: 12px;
  font-weight: 100;
  font-family: Pirulen, Arial, Helvetica, sans-serif;
  color: #00ffff;
  text-align: center;
  display: inline-block;
  min-width: 140px;
}

.vAddy2 {
  font-size: 12px;
  font-weight: 100;
  font-family: Pirulen, Arial, Helvetica, sans-serif;
  color: #00ffff;
  text-align: center;
  display: inline-block;
  min-width: 140px;
  margin-bottom: 24px;
}

.vAddy11 {
  font-size: 12px;
  font-weight: 100;
  padding-top: 10px;
  font-family: Pirulen, Arial, Helvetica, sans-serif;
  color: #00ffff;
  text-align: center;
  display: inline-block;
  min-width: 140px;
}

.walBalT {
  color: #00ffff;
  margin: 10px;
  font-size: 28px;
  font-weight: 400;
}

.neatStaking {
  text-align: left;
  margin: 10px;
}
.walimgs {
  width: 28px;
  height: auto;
}

.walimg {
  width: 64px;
  height: auto;
  margin: 0;
}

.spinr {
  margin: 0 auto;
  display: inline-block;
}

.balance-details {
  text-align: center;
  margin-top: 10px;
}
.dashboard {
  font-weight: bold;
  color: #00ffff;
  padding-top: 10px;
}
.pools {
  margin: 10px auto;
}

.btnss {
  margin-bottom: -10px;
}

.btns4 {
  margin-bottom: -20px;
}

.rippleStake {
  font-size: 12px;
  min-width: 68px;
  height: 22px;
  border-radius: 4px;
  font-weight: bold;
  color: #00ffff;
  border: 1px solid #00ffffa4;
  background-color: transparent;
  background-position: center;
  transition: background 0.4s;
  margin: 0 10px;
}

.rippleStake:hover {
  color: #000;
  text-transform: uppercase;
  background: #00ffff radial-gradient(circle, transparent 1%, red 1%)
    center/15000%;
}

.rippleSelect {
  font-size: 12px;
  min-width: 68px;
  height: 22px;
  border-radius: 4px;
  font-weight: bold;
  color: #00ffff;
  border: 1px solid #00ffffa4;
  background-color: transparent;
  background-position: center;
  transition: background 0.4s;
  margin: 0 10px;
}

.rippleSelect:hover {
  color: #000;
  text-transform: uppercase;
  background: #00ffff radial-gradient(circle, transparent 1%, red 1%)
    center/15000%;
}

.rippleClaims {
  font-size: 12px;
  min-width: 68px;
  height: 22px;
  border-radius: 4px;
  font-weight: bold;
  border: 1px solid #00ffffa4;
  background-color: transparent;
  background-position: center;
  transition: background 0.4s;
  margin: 0 10px;
}

.rippleClaims:hover {
  color: #000;
  text-transform: uppercase;

  background: #00ffff radial-gradient(circle, transparent 1%, #00ffff 1%)
    center/15000%;
}

.deleg {
  text-align: center;
  margin: 10px 0px;
  font-size: 13px;
  font-weight: 100;
  color: #496785;
  font-family: Pirulen, Helvetica, sans-serif;
}

.noSel {
  text-align: center;

  margin: 10px 0px;
  font-size: 16px;
  font-weight: 100;
  color: #496785;
  font-family: Pirulen, Helvetica, sans-serif;
}

.addry-w {
  text-align: center;

  font-size: 16px;
  font-weight: 100;
  color: #496785;
  font-family: Pirulen, Helvetica, sans-serif;
}

.boxess {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
  padding: 20px 0px;
}

@media only screen and (max-width: 560px) {
  .box1 {
    width: auto;
    min-height: 300px;
    padding-top: 10px;
    border-width: 1px;
    background: #000;
    display: grid;
    border-radius: 10px;
    margin: 50px 10px 0px 10px;
    box-sizing: 1px;
    border: none;
    border: 1px solid #00ffffa4;
    border-radius: 10px;
    box-shadow: 0 0 40px #00bfff31;
  }

  .valueD {
    font-family: Helvetica, sans-serif;
    color: #00ffff;
    font-size: 12px;
    font-weight: lighter;
    margin-bottom: 5px;
  }

  .pools {
    text-align: center;
    margin: 0 auto;
    padding: 10px;
  }

  .rippleStake {
    font-size: 12px;
    min-width: 68px;
    height: 22px;
    border-radius: 4px;
    font-weight: bold;
    color: #00ffff;
    border: 1px solid #00ffffa4;
    background-color: transparent;
    background-position: center;
    transition: background 0.4s;
    margin: 0 auto;
  }

  .rippleStake:hover {
    color: #000;
    text-transform: uppercase;
    background: #00ffff radial-gradient(circle, transparent 1%, red 1%)
      center/15000%;
  }

  .rippleClaims {
    font-size: 12px;
    min-width: 68px;
    height: 22px;
    border-radius: 4px;
    font-weight: bold;
    border: 1px solid #00ffffa4;
    background-color: transparent;
    background-position: center;
    transition: background 0.4s;
    margin: 0 auto;
  }

  .rippleClaims:hover {
    color: #000;
    text-transform: uppercase;

    background: #00ffff radial-gradient(circle, transparent 1%, #00ffff 1%)
      center/15000%;
  }

  #myGrid {
    flex: 1 1 0px;
    width: 100%;
  }

  .box2 {
    margin: 60px 10px;
  }
}
</style>


