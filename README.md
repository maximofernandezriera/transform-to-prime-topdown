# transform-to-prime-topdown

    public static int minimumNumber(int[] numbers) {
        int sum = 0;
        for (int num : numbers) {
            sum += num;
        }

        int target = findClosestPrime(sum);
        return target - sum;
    }

    private static int findClosestPrime(int num) {
        while (!isPrime(num)) {
            num++;
        }
        return num;
    }

    private static boolean isPrime(int num) {
        if (num < 2) {
            return false;
        }
        for (int i = 2; i <= Math.sqrt(num); i++) {
            if (num % i == 0) {
                return false;
            }
        }
        return true;
    }
